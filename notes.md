

<h1>Notes</h1>
<div class="posts">
  {% for post in site.categories.Articles %}
    <article class="post">

    <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}}
      </div>
    </article>
  {% endfor %}
</div>
