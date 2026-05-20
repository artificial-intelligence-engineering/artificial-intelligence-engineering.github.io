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

      [teaser, body].forEach(function (el) {
        if (!el) return;

        el.addEventListener("click", function (event) {
          // Keep native behavior for existing links/buttons inside the card.
          if (event.target.closest("a, button")) return;
          window.location.href = targetUrl;
        });
      });
    });
  });
</script>
