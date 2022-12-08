---
layout: page
category: recits
lang: FR
ref: recits
---
 {% assign pages=site.pages | where:"ref", page.ref | sort: 'lang' %}
  {% for page in pages %}
    
      <a class="selector" href="{{ page.url }}" class="{{ page.lang }}" {% if page.lang == page.lang %}style="border-bottom: 5px solid #222"{% endif %}>{{ post.lang }}</a>  
  {% endfor %}
    

<h1>Récits</h1>


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


