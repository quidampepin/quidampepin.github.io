---
layout: page
lang: FR
ref: index
category: Home
---

<section class="hero">
  <img class="hero__photo" src="{{ site.baseurl }}/images/David_Pepin_landing.jpg" alt="" width="112" height="112" decoding="async">
  <div>
    <h1 class="hero__title">Écriture, design et gouvernement numérique</h1>
    <p class="hero__lead">
      Bienvenue dans mon espace de publication personnel, un lieu dédié à de courts essais, à différentes expériences d'écriture et à des fictions occasionnelles.
    </p>
    <p class="hero__links">
      <a href="{{ site.data.snippets.FR.portfoliourl }}">Portfolio</a>
      <a href="{{ site.data.snippets.FR.projectsurl }}">Projets</a>
      <a href="{{ site.data.snippets.FR.biourl }}">À propos de moi</a>
    </p>
  </div>
</section>

<h2 class="section-label">Textes récents</h2>

{% assign posts = site.posts | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang heading="h3" %}
