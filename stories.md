---
layout: page
category: recits
lang: EN
ref: recits
title: Fiction
---

<header class="page-intro">
  <h1>Fiction</h1>
  <p class="lead">Short stories and other narrative texts.</p>
</header>

{% assign posts = site.categories.recits | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang %}
