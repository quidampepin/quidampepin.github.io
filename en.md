---
layout: page
lang: EN
ref: index
category: Home
---

<section class="hero">
  <div class="hero__text">
    <h1 class="hero__title">Writing, design, and digital government</h1>

    <p class="hero__lead">
      Welcome to my personal publishing space — a place for short essays, small experiments, and occasional fiction.
    </p>

    <p class="hero__body">
      I write most posts in French first, and then make an English translation available.
    </p>
  </div>

  <div class="hero__media">
    <img
      class="hero__photo"
      src="{{ site.baseurl }}/images/David_Pepin.jpg"
      alt="Photo of David Pepin"
      loading="lazy"
      decoding="async"
    />
  </div>
</section>

<div class="posts">
  

  {% assign posts=site.posts | where:"lang", page.lang %}
  {% for post in posts %}
    <article class="post" style="border-top: 2px solid #ccc;">

       <h2 style="margin-bottom:0">
   
      {{ post.title }}
      </h2>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}} - {{ post.tag }}
      </div>
       <p style="margin-top: .5em;">
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Read "{{ post.title }}"</a>
      </p>


  

    </article>
  {% endfor %}
</div>
