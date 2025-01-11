---
layout: default
---

<div class="posts-container">
  {% for post in site.posts %}
  <article class="post-card">
    <h1>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h1>
    
    <div class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </div>

    <div class="post-excerpt">
      {{ post.excerpt }}
    </div>

    <a href="{{ post.url }}" class="read-more">Read More →</a>
  </article>
  {% endfor %}
</div>