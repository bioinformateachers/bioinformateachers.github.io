---
layout: default
---

[List of posts by category](./categories.html).
 | [All posts](./blog.html).

<h1>{{ site.posts.first.title }}</h1>
{{ site.posts.first.content | replace: "\[", "\\\[" | replace: "\]", "\\\]" }}

$$y = x^2 + \phi$$

[back](./)
