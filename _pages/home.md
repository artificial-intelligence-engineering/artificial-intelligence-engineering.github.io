---
layout: splash
permalink: /
hidden: true
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/mm-home-page-feature.jpg
excerpt: >
  <div style="display: flex; gap: 1.5rem; align-items: flex-start;">
    <div style="flex: 1; color: #fff;">
      AI Engineering is a new discipline that is constantly evolving. On this site,
      we compile all related information, such as tools, frameworks, glossaries, best practices,
      and resources for further study.
    </div>
    <div style="flex: 0 0 32%; font-style: italic; font-size: 0.9em; line-height: 1.4; color: #fff;">
      "We are no longer asking how to build models; we're asking how to build products that use models." -- Chip Huyen, AI Engineering: Building Applications with Foundation Models
    </div>
  </div>
feature_row:
  - image_path: /assets/images/mm-customizable-feature.png
    alt: "customizable"
    title: "Application Development"
    excerpt: "AI Interface, Prompt Engineering, Context Enrichment, Evaluation."
    url: "/application-development/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /assets/images/mm-responsive-feature.png
    alt: "fully responsive"
    title: "Model Development"
    excerpt: "Inference Optimization, Dataset Engineering, Fine tuning."
    url: "/model-development/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /assets/images/mm-free-feature.png
    alt: "100% free"
    title: "AI Infrastructure"
    excerpt: "Development Orchestration, Production Delivery, AI Patterns, Monitoring."
    url: "/ai-infrastructure/"
    btn_class: "btn--primary"
    btn_label: "Learn more"      
---

{% include feature_row %}

<style>
  .feature__item .archive__item-teaser,
  .feature__item .archive__item-body {
    cursor: pointer;
  }

  .feature__item .archive__item-teaser {
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    background: #d9d9e3;
    box-shadow: 0 10px 24px rgba(0, 0, 0, 0.12);
  }

  .feature__item .archive__item-teaser img {
    display: block;
    width: 100%;
    filter: saturate(1.35) contrast(1.08) brightness(1.03);
    transition: transform 0.25s ease, filter 0.25s ease;
  }

  .feature__item .archive__item-teaser::after {
    content: "";
    position: absolute;
    inset: 0;
    pointer-events: none;
    opacity: 0.35;
  }

  .feature__item:nth-child(1) .archive__item-teaser::after {
    background: linear-gradient(135deg, rgba(89, 97, 255, 0.45), rgba(76, 201, 240, 0.2));
  }

  .feature__item:nth-child(2) .archive__item-teaser::after {
    background: linear-gradient(135deg, rgba(0, 180, 140, 0.4), rgba(72, 149, 239, 0.2));
  }

  .feature__item:nth-child(3) .archive__item-teaser::after {
    background: linear-gradient(135deg, rgba(255, 140, 66, 0.4), rgba(255, 0, 110, 0.18));
  }

  .feature__item:hover .archive__item-teaser img {
    transform: scale(1.03);
    filter: saturate(1.5) contrast(1.1) brightness(1.05);
  }
</style>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    var items = document.querySelectorAll(".feature__item");

    items.forEach(function (item) {
      var button = item.querySelector(".btn");
      if (!button || !button.href) return;

      var targetUrl = button.href;
      var teaser = item.querySelector(".archive__item-teaser");
      var body = item.querySelector(".archive__item-body");

      function bindCardClick(el) {
        if (!el) return;

        el.addEventListener("click", function (event) {
          if (event.target.closest("a, button")) return;
          window.location.href = targetUrl;
        });
      }

      bindCardClick(teaser);
      bindCardClick(body);
    });
  });
</script>
