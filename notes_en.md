---
layout: page
category: Notes
lang: EN
ref: notes
title: Notes
---

<header class="page-intro">
  <h1>Notes</h1>
  <p class="lead">Short notes, links and other ideas.</p>
</header>

{% assign posts = site.categories.Notes | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang %}
