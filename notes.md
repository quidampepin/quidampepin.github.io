---
layout: page
category: Notes
lang: FR
ref: notes
title: Notes
---

<header class="page-intro">
  <h1>Notes</h1>
  <p class="lead">Courtes notes, liens et autres idées.</p>
</header>

{% assign posts = site.categories.Notes | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang %}
