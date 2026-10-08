---
header_type: "hero"
header_img : "https://picsum.photos/id/1018/2000/2000"
title: Current skin
subtitle: Bootstrap components with the current skin
last_modified_at: 2021-02-03
tags: [skin, bootstrap, current-theme, header-hero, image, demo]
categories: [skins]
---

This page shows how Bootstrap components look with the current theme
configuration.

{% if page.show_bottomnavs -%}
{% include components/navbeforeafter.html -%}
{% endif -%}
{% if page.show_categories -%}
{% include components/categories.html-%}
{% endif -%}
{% if page.show_tags -%}
{% include components/tags.html-%}
{% endif -%}

{% include snippets/bootstrapdemo.html  %}
