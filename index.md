---
layout: default
---

{% for post in site.posts %}

# [{{ post.title }}]({{ post.url }})

*Posted on {{ post.date | date: "%Y-%m-%d" }}*

{{ post.excerpt }}

[Read More]({{ post.url }})

{% endfor %}
