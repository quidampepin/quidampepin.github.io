

<h1>Billets</h1>
<div class="posts">
  {% for post in site.categories.Billets %}
  <article class="post">

   <h3 style="margin-bottom:0">
   
   <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      </h3>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}}
      </div>
       <p style="margin-top: .5em;">
        {{ post.description }}
      </p>

  </article>
    
  {% endfor %}
</div>