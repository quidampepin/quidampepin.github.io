---
layout: page
category: Billets
lang: FR
ref: billets
title: Blogue
---

<header class="page-intro">
  <h1>Blogue</h1>
  <p class="lead">Billets de blogue à propos de divers sujets.</p>
</header>

{% assign posts = site.categories.Billets | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang %}
