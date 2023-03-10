---
layout: default
title: List of all posts in the blog
---

<ul>
{% for post in site.posts %}
 <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

{% if page.author %}
  {% include author/{{page.author}}.html %}
{% endif %}

[back](./)
