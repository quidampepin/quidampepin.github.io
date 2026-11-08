---
layout: page
lang: EN
ref: index
category: Home
---

<section class="hero">
  <img class="hero__photo" src="{{ site.baseurl }}/images/David_Pepin_landing.jpg" alt="" width="112" height="112" decoding="async">
  <div>
    <h1 class="hero__title">Writing, design, and digital government</h1>
    <p class="hero__lead">
      Welcome to my personal publishing space, a place for short essays, different writing experiments, and occasional fiction.
    </p>
    <p class="hero__links">
      <a href="{{ site.data.snippets.EN.portfoliourl }}">Portfolio</a>
      <a href="{{ site.data.snippets.EN.projectsurl }}">Projects</a>
      <a href="{{ site.data.snippets.EN.biourl }}">About me</a>
    </p>
  </div>
</section>

<h2 class="section-label">Latest writing</h2>

{% assign posts = site.posts | where: "lang", page.lang %}
{% include post-list.html posts=posts lang=page.lang heading="h3" %}
