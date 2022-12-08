---
category: recits
lang: FR
ref: recits
---

<h1>Récits</h1>
 <a class="selector" href="/recits/" style="border-bottom: 5px solid #222">FR</a>  
 <a class="selector" href="/stories/">EN</a>   

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
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Lire le reste de "{{ post.title }}"</a>

      </p>

  </article>
    
  {% endfor %}
</div>


