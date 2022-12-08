---
layout: default
lang: en
ref: index
---

<h1>Bienvenue</h1>

<div style="max-width: 65ch;">


  <p>Englis test - Bienvenue dans mon espace de publication personnel. Les opinions et les idées présentées ici n'engagent que moi, et ne représenent pas l'opinion de mon employeur. </p>  


<p>Je suis un <a href="https://wiki.gccollab.ca/Agents_libres_du_Canada">agent libre du Canada</a>, présentement à l'emploi de l'Agence de la Santé Publique du Canada. </p>
   </div>
<div class="posts">
  
  <h2>Last entries</h2>
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
