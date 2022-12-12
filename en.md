---
layout: page
lang: EN
ref: index
category: Home
---

<h1>Welcome</h1>



Welcome to my personal publishing space!
 
Why not just talk about a blog? Because it won't just be a space for posting blog posts. There will also be short fiction texts, as well as notes, to quickly share a link or an idea.

In short: a place to publish my writing experiments.

I write most posts in French first, and then make the translation available. 

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
