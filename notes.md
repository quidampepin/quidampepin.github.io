

<h1>Notes</h1>
<div class="posts">
  {% for post in site.categories.Notes %}
   <article class="post">

   <h3 style="margin-bottom:0">
   
   <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      </h3>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}}
      </div>
           <p style="margin-top: .5em;">
        {{ post.excerpt }} <a href="{{ site.baseurl }}{{ post.url }}" class="read-more"><span class="fa fa-arrow-right"></span> Lire le reste</a>
      </p>


   </article>
    
  {% endfor %}
</div>
