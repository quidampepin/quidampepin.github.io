

<h1>Notes</h1>
<div class="posts">
  {% for post in site.categories.Notes %}
    <article class="post">

    <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
 <p>
        {{ post.description }}
      </p>
      <div class="date">
        {{ post.date | date: "%Y-%m-%d"}}
      </div>
    </article>
  {% endfor %}
</div>
