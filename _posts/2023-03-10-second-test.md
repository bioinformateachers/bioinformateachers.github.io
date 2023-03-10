---
layout: post
title:  "Another test post with branches"
date:   2023-03-10 10:00:01 +0100
categories: jekyll update
author: pippo
---

# This is our test post

This is test *content*

$$
\frac{\partial f(x)}{ \partial x}
$$

{% if page.author %}
  {% include author/{{page.author}}.html %}
{% endif %}
