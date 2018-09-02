---
layout: default
title: Activities
permalink: /activities/
---


##  Activities
<p style='text-align: justify;'>
This page contains activities (including conferences and workshops) that I have attended/participated in.
</p>

{% for post in site.categories.activity %}
- ### {{ post.date | date_to_string }} » [{{ post.title }}]({{ site.baseurl }}{{ post.url }}) » {{post.location}}
{{ post.excerpt }}
{% endfor %}
