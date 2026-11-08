---
layout: page
category: recits
lang: FR
ref: recits
title: Fiction
---

<header class="page-intro">
  <h1>Fiction</h1>
  <p class="lead">Nouvelles et autres textes narratifs.</p>
</header>

{% assign posts = site.categories.recits | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang %}
