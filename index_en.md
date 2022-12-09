---
layout: page
lang: EN
ref: index
Category: Home
---

<h1>Welcome</h1>



 Welcome to my personal publishing space!
 
 Blog posts, fiction, scattered notes: a place to publish writing experiments.

<div class="posts">
  
  <h2>Latest entries</h2>
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
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Read the rest of "{{ post.title }}"</a>
      </p>


  

    </article>
  {% endfor %}
</div>
