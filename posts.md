---
layout: page
category: Billets
lang: EN
ref: billets
title: Blog
---

<header class="page-intro">
  <h1>Blog</h1>
  <p class="lead">Blog posts about various topics.</p>
</header>

{% assign posts = site.categories.Billets | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang %}
