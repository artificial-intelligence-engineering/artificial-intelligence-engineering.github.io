# AGENTS.md

## Project snapshot
- Treat this repository as a **Jekyll static site**. Author source content in `_pages/` and `_posts/`; do **not** edit generated output in `_site/`.
- Site-wide behavior lives in `_config.yml` and `Gemfile`, using the remote theme `mmistakes/minimal-mistakes` plus Jekyll plugins.
- Use `_pages/overview.md` to understand the site’s organizing model: **Application Development**, **Model Development**, **AI Infrastructure**, and **AI Governance**.

## Actions coding agents must never take
- Do **not** run destructive or state-changing `git` commands, including `git add`, `git commit`, and `git push`, or any command that modifies the local or remote repository state. Never create new branches (git bracn), never create worktrees. All of this git
operations are resposibility of the human (developer).
- Do **not** run `bundle install` or `bundle exec jekyll serve`; these tasks are reserved for the human operator.
- If a task would normally require installing dependencies, serving the site locally, or writing repository state, stop after preparing file changes and hand execution back to the human.

## Human workflow reference
- The documented local workflow is `bundle install` followed by `bundle exec jekyll serve`.
- If local Ruby SSL verification blocks gem access, `utils/run.sh` shows the repository’s fallback via `utils/disable-local-ssl-verify.rb`.
- `_config.yml` is **not** hot-reloaded by Jekyll; changes there require a server restart.
- There is no discoverable automated test suite; typical validation is a clean Jekyll build/serve plus visual inspection of rendered pages.

## Content model and boundaries
- Keep permanent site sections in `_pages/` with explicit `permalink` values; examples include `_pages/overview.md`, `_pages/glossary.md`, `_pages/research.md`, and `_pages/lxm.md`.
- Keep dated blog content in `_posts/` using `YYYY-MM-DD-*.md`; post permalinks are controlled globally by `/:categories/:title/` in `_config.yml`.
- Update `_data/navigation.yml` when adding a new top-level page that should appear in site navigation.
- Treat `agents/` as maintenance guidance for specific content areas, not as user-facing site content.

## Editing conventions specific to this repo
- Preserve **YAML front matter** on every page and post. Many pages override defaults from `_config.yml`; for example, `_pages/research.md` disables `author_profile` and enables TOC settings.
- Preserve inline HTML when editing content. Several important pages rely on hand-authored HTML tables rather than plain Markdown.
- `_pages/lxm.md` is a special page with `layout: splash`, inline JavaScript for sticky ecosystem navigation, and a large HTML table with per-ecosystem anchor rows and external favicon URLs.
- `_pages/research.md`, `_pages/glossary.md`, and `_pages/ai-agent.md` also depend on custom HTML tables; keep tag balance, column order, and row patterns intact.
- `_pages/overview.md` embeds a large inline SVG; avoid restructuring it unless the task explicitly requires SVG edits.

## Page patterns to follow
- For new permanent pages, mirror the structure used in `_pages/overview.md` or `_pages/research.md`: explicit `permalink`, `layout`, and optional `author_profile` / `toc` settings.
- For blog posts, follow `_posts/2010-01-08-post-chat.md`: front matter with `title`, `categories`, and `tags`.
- Reference assets with site-root paths such as `/assets/images/...`.

## Specialized agent instructions
- For LxM ecosystem table work, read `agents/AGENTS_LXM.md` first and keep edits scoped to the target table in `_pages/lxm.md`.
- For landmark research paper updates, read `agents/AGENTS_RESEARCH.md` first and keep edits scoped to the target table in `_pages/research.md`.
- Treat `agents/LANGFLOW.md` as reference material, not as an active repository-wide instruction file.
- Prefer minimal, tightly scoped edits throughout this repo; accidental HTML breakage is a bigger risk than conventional code regressions.
