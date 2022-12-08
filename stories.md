---
category: recits
lang: EN
ref: recits
---

<h1>Fiction</h1>
<div class="posts">

  {% assign posts=site.categories.recits | where:"lang", page.lang %}
  {% for post in posts %}

  <article class="post">

  <h3 style="margin-bottom:0">
   
{{ post.title }}
      </h3>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}}
      </div>
          <p style="margin-top: .5em;">
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Read the rest of "{{ post.title }}"</a>

      </p>

  </article>
    
  {% endfor %}
</div>


