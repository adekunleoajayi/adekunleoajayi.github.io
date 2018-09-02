---
layout: default
title: Blog
permalink: /blog/
---


##  Blog Post
{% for post in site.categories.blog %}
- ### {{ post.date | date_to_string }} » [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{{ post.excerpt  }}
{% endfor %}


<!---
{% if post.excerpt != post.content %}
<a href="{{ site.baseurl }}{{ post.url }}">Read more</a>
{% endif %}
-->
