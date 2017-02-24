---
layout: default
title: Posts
permalink: /posts/
---


## Recent posts
{% for post in site.posts %}
- {{ post.date | date_to_string }} » [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}
