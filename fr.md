---
layout: page
lang: FR
ref: index
category: Home
---

<h1>Bienvenue</h1>


  Bienvenue dans mon espace de publication personnel!
  
  Pourquoi ne  pas parler simplement d’un blogue? Parce que ce ne sera pas uniquement un espace pour publier des billets de blogue. Il y aura aussi de courts textes de fiction, de même que des notes, pour partager un lien ou une idée.

  En bref: un endroit où publier mes expériences d'écriture. 

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
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Lire « {{ post.title }} »</a>
      </p>


  

    </article>
  {% endfor %}
</div>
