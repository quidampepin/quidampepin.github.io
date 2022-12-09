---
layout: page
lang: FR
ref: index
Category: Home
---

<h1>Bienvenue</h1>


  Bienvenue dans mon espace de publication personnel!
  
  Des billets de blogue, des textes de fiction, des notes éparpillées : un endroit où déposer des expériences d'écriture. 

<div class="posts">
  
  <h2>Dernières entrées</h2>
   {% assign posts=site.posts | where:"lang", page.lang %}
  {% for post in posts %}
    <article class="post">

       <h3 style="margin-bottom:0">
   
      {{ post.title }}
      </h3>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}} - {{ post.tag }}
      </div>
       <p style="margin-top: .5em;">
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Lire le reste de « {{ post.title }} »</a>
      </p>


  

    </article>
  {% endfor %}
</div>
