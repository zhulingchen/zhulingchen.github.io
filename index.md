---
layout: default
---

# Latest Posts

{% raw %}{% for post in site.posts %}
## [{{ post.title }}]({{ post.url }})

*Posted on {{ post.date | date: "%Y-%m-%d" }}*

{{ post.excerpt }}

[Read more]({{ post.url }})

---
{% endfor %}{% endraw %}
