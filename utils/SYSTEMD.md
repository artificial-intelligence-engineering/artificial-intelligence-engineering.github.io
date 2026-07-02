# Systemd Review

## Intro

The first step in the boot process is to load the Linux kernel, which is the main
component of the Linux operating system. Once the kernel is loaded, it initializes
the hardware and starts the systemd process, which is the first process that runs
on the system. So systemd is the first user-space process started by the Linux
kernel and runs with PID 1.

Once the kernel loads systemd, systemd takes over and starts the other system
services that are required to bring the system up and running. So systemd is
the mother of all processes. It is responsible for bringing the Linux host up
to a STATE in which productive work can be done. También es responsable de llevar
al host al estado de apagado.

Lo primero que hace systemd es montar los filesystems usando las instrucciones
de /etc/fstab (filesystem table). De esta forma puede acceder a los ficheros que
instruyen el arranque deseado.

## D-BUS and sockets

Es muy importante entender que: systemd provides aggressive parallelization
capabilities, uses socket and D-Bus activation for starting services.

## Systemd Targets and Systemd Units

Systemd uses TARGETS to define system STATES, replacing traditional runlevels.
Targets group services, sockets, and other units required to reach a specific
operating mode.

A SYSTEMD UNIT is a managed resource (service, socket, mount, timer, etc.);
a UNIT FILE is the configuration file that defines that unit.

Unit files are read from several directories. When loading a unit, systemd searches
these paths in a fixed precedence order and picks the first (highest-priority).  
Knowing this order tells you where to place custom or modified unit files so  
they are not overwritten by package updates and so your changes take effect.

### Prioridad de busqueda de units files

| Directory | Priority (1 = highest) | When to use |
| --- | --- | --- |
| `/etc/systemd/system/` | 1 | Custom unit files and overrides. Survives reboots and is not overwritten by packages. Use for new services or to fully replace a vendor unit. |
| `/run/systemd/system/` | 2 | Runtime-only units. Highest priority after `/etc`. Changes are lost on reboot. Used by systemd and by installers for temporary overrides. |
| `/lib/systemd/system/` (or `/usr/lib/systemd/system/`) | 3 | Vendor- and package-supplied units. Do not edit; override via `/etc/systemd/system/` or drop-in files instead. |

## Systemd Targets

In systemd, a target represents a system state or milestone, not a process or
a service.  A service is started as part of a target by declaring that it  
should be started when systemd is trying to reach that target.

When systemd activates a target, it starts all services that are wanted by
that target, respecting dependency and ordering rules.

A unit configuration file whose name ends in **".target"** encodes information
about a target unit of systemd. Target units are used to group units and to set
synchronization points for ordering dependencies with other unit files.

Técnicamente un target en realidad es un systemd unit file que agrupa otros unit files.

Para ver los targets de nuestro sistema (activos):

```bash
systemctl list-units --type=target
```

Para ver el target por defecto:

```bash
systemctl get-default
```

Para cambiar entre targets (hay que entender que al cambiar de target en caliente
se detienen todos los servicios que no pertenezcan al target indicado e inicia los
que sí pertenecen.)

```bash
# Cambio inmediato (sesión actual, en caliente)
systemctl isolate <nombre-del-target>

    # Cambiar a modo texto (sin interfaz gráfica)
    systemctl isolate multi-user.target

    # Cambiar a modo gráfico
    systemctl isolate graphical.target

    # Cambiar a modo rescate (single user)
    systemctl isolate rescue.target

    # Cambiar a modo emergencia (mínimo)
    systemctl isolate emergency.target

# Cambio permanente (sobrevive al reboot, es el target por defecto)
systemctl set-default <nombre-del-target>

    # Ejemplo: arrancar siempre en modo texto
    systemctl set-default multi-user.target

    # Ejemplo: arrancar siempre en modo gráfico
    systemctl set-default graphical.target
```

### Targets más comunes

| Target | Equivalente SysV | Descripción |
| --- | --- | --- |
| `default.target` | NA | This target is always aliased with a symbolic link to either multi-user.target or graphical.target. systemd always uses the default.target to start the system. The default.target should never be aliased to halt.target, poweroff.target, or reboot.target. |
| `poweroff.target` | runlevel 0 | Apagar el sistema |
| `rescue.target` | runlevel 1 | Modo usuario único (rescate). A basic system including mounting the filesystems with only the most basic services running and a rescue shell on the main console. |
| `multi-user.target` | runlevel 3 | Modo texto multiusuario |
| `graphical.target` | runlevel 5 | Modo gráfico |
| `reboot.target` | runlevel 6 | Reiniciar el sistema |
| `emergency.target` | single-user | Shell mínimo, solo root montado en solo lectura. No services are running; filesystems are not mounted. This is the most basic level of operation with only an emergency shell running on the main console for the user to interact with the system. Single-user mode in SystemV. |

Unless otherwise changed at boot time in the GRUB menu, systemd always starts the  
default.target. The default.target file is a symbolic link to the true target file.
For a desktop workstation, this is typically going to be the graphical.target, which
is equivalent to runlevel 5 in SystemV. For a server, the default is more likely to
be the multi-user.target, which is like runlevel 3 in SystemV. The emergency.target
file is similar to single-user mode. Targets and services are systemd units.

## Systemd Units

If you have run ```systemctl status nginxs```, the output you saw – the service state,  
PID, memory usage, recent log lines, and whether it is enabled at boot – describes  
a **systemd unit**. A unit is the object systemd tracks and manages. A unit file is  
the configuration file on disk that tells systemd what the unit is, how to start it,  
what it depends on, and when it should run.

Units are not limited to services. systemd uses the same model to manage network sockets,  
filesystem mount points, swap devices, hardware devices, scheduled tasks, and system  
state checkpoints. Each type has its own unit file suffix and its own section in the  
unit file for type-specific configuration.

### Unit files common .prefix

Un incompleta lista de las extensiones (suffix) usadas por systemd:

| Extensión | Tipo de unit | Descripción |
| --- | --- | --- |
| `.service` | Service | Proceso o demonio del sistema (el tipo más común). |
| `.socket` | Socket | Socket IPC, de red o de fichero. Permite activación por socket. |
| `.target` | Target | Agrupación lógica de units (similar a los runlevels de SysV). |
| `.mount` | Mount | Punto de montaje del sistema de ficheros (equivale a una entrada en `/etc/fstab`). |
| `.automount` | Automount | Montaje automático bajo demanda de un sistema de ficheros. |
| `.swap` | Swap | Dispositivo o fichero de intercambio (swap). |
| `.timer` | Timer | Temporizador que activa otra unit de forma programada (alternativa a `cron`). |
| `.path` | Path | Monitorización de cambios en ficheros o directorios. Activa otra unit cuando se detecta un cambio. |
| `.device` | Device | Dispositivo del kernel expuesto a través de `udev`. |
| `.slice` | Slice | Agrupación jerárquica de recursos con cgroups (CPU, memoria, I/O). |
| `.scope` | Scope | Conjunto de procesos externos creados en tiempo de ejecución (no se definen con ficheros, los crea systemd programáticamente). |
| `.snapshot` | Snapshot | *(Obsoleto)* Estado guardado del sistema en un momento dado. Eliminado en versiones recientes de systemd. |

Listar unit files por tipo:

```bash
# Listar todas las units cargadas
systemctl list-units

# Filtrar por tipo (units)
systemctl list-units --type=service
systemctl list-units --type=timer
systemctl list-units --type=mount

# Listar todos los ficheros de unit instalados (unit files)
systemctl list-unit-files

# Filtrar por tipo
# Solo servicios
systemctl list-unit-files --type=service

# Solo timers
systemctl list-unit-files --type=timer

# Solo targets
systemctl list-unit-files --type=target

# Solo sockets
systemctl list-unit-files --type=socket

# Solo mounts
systemctl list-unit-files --type=mount

# Filtrar por estado

# Solo los habilitados
systemctl list-unit-files --state=enabled

# Solo los deshabilitados
systemctl list-unit-files --state=disabled

# Solo los estáticos (no se pueden habilitar/deshabilitar directamente)
systemctl list-unit-files --state=static

# Solo los enmascarados (masked)
systemctl list-unit-files --state=masked

# Combinar varios estados
systemctl list-unit-files --state=enabled,disabled

# Combinar filtros

# Servicios habilitados
systemctl list-unit-files --type=service --state=enabled

# Timers deshabilitados
systemctl list-unit-files --type=timer --state=disabled
```

### Posibles estados de los unit files

| Estado | Significado |
| --- | --- |
| `enabled` | Se inicia automáticamente (tiene enlace simbólico en un target). |
| `disabled` | Instalado pero no se inicia automáticamente. |
| `static` | No tiene sección `[Install]`; solo se activa como dependencia de otra unit. |
| `masked` | Completamente bloqueado (enlazado a `/dev/null`). No se puede iniciar. |
| `indirect` | No se habilita directamente; se activa a través de otra unit (`Also=`). |
| `generated` | Generado automáticamente por un generador de systemd (ej. desde `/etc/fstab`). |
| `transient` | Creado en tiempo de ejecución de forma dinámica. |
| `bad` | El fichero de unit tiene errores de sintaxis o es inválido. |
| `alias` | Es un alias (enlace simbólico) a otra unit. |
| `linked` | Enlazado manualmente desde una ruta fuera de los directorios estándar de systemd. |

## Analyzing systemd Startup

The systemd system provides the ```systemd-analyze``` tool that can help us discover performance
and other important systemd information.

### Basic Analysis

This command performs a very basic analysis that looks at the overall times for each stage
of boot and startup. This can be done as a non-root user.

```bash
$ systemd-analyze
    Startup finished in 53.951s (firmware) + 6.606s (loader) + 2.061s (kernel) + 5.956s (initrd) + 8.883s (userspace) = 1min 17.458s
    graphical.target reached after 8.850s in userspace.
```

### Blame Analysis

We can use systemd-analyze blame to discover which systemd units take the most time to initialize.
This provides much more detail and enables us to see what portions of the startup process take
the most time.

The results are displayed in order by the amount of time they took to initialize from
highest to lowest. You can do this as a non-root user.

```bash
$ systemd-analyze blame
       2min 30.408s fstrim.service
     33.971s vboxdrv.service
      5.832s dev-disk-by\x2dpartuuid-4212eea1\x2d96d0\x2dc341\x2da698\x2d18a0752f034f.device
      5.832s dev-disk-by\x2ddiskseq-1\x2dpart1.device
      5.832s dev-sda1.device
<SNIP – removed lots of entries with increasingly small times>
```

Because many of these services start in parallel, the numbers from this command may
add up to equal significantly more than the total given by systemd-analyze time for
everything that comes after the BIOS. The number of units that can truly start in
parallel is determined by the number of CPUs in your host.

The data from this command can provide indicators of which services we might look
at to improve boot times. Services that are not used can be disabled

### Critical Chain Analysis

Like the critical path in project management, the critical chain shows the
time-critical chain of events that took place during startup. These are the
systemd units you want to look at if the startup is slow—they are the ones
that would be causing the delays. This tool does not display all units that
started, only those in this critical chain of events.

```bash
$ systemd-analyze critical-chain
The time when unit became active or started is printed after the "@" character.
The time the unit took to start is printed after the "+" character.
graphical.target @8.850s
└─multi-user.target @8.849s
  └─vboxweb-service.service @8.798s +38ms
    └─network-online.target @8.776s
      └─NetworkManager-wait-online.service @4.932s +3.843s
        └─NetworkManager.service @4.868s +39ms
          └─network-pre.target @4.850s
            └─dkms.service @3.438s +1.411s
              └─basic.target @3.409s
                └─dbus-broker.service @3.348s +55ms
                  └─dbus.socket @3.309s
                    └─sysinit.target @3.267s
                      └─systemd-binfmt.service @2.814s +452ms
                        └─proc-sys-fs-binfmt_misc.mount @3.232s +21ms
                          └─proc-sys-fs-binfmt_misc.automount @967ms
```

The numbers with “@” preceding them show the absolute number of seconds since
startup began at which the unit becomes active. The numbers preceded by “+”
show the amount of time it takes for the unit to start.

### System State Analysis

You may sometimes need to determine the current state of the system. The
systemd-analyze dump command dumps a massive amount of data about the
current system state.
