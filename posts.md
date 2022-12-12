---
category: Billets
lang: EN
ref: billets
---


<h1>Blog</h1>

Blog posts about various topics.

<div class="posts">
  {% assign posts=site.categories.Billets | where:"lang", page.lang %}
  {% for post in posts %}

  <article class="post" style="border-top: 2px solid #ccc;">

   <h3 style="margin-bottom:0">
   
   {{ post.title }}
      </h3>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}}
      </div>
          <p style="margin-top: .5em;">
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Read "{{ post.title }}"</a>
      </p>

  </article>
    
  {% endfor %}
</div>
