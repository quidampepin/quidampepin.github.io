---
category: Billets
lang: FR
ref: billets
---


<h1>Blogue</h1>

Billets de blogue à propos de divers sujets.

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
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Lire « {{ post.title }} »</a>
      </p>

  </article>
    
  {% endfor %}
</div>
