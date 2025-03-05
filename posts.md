---
layout: page
title: Posts
permalink: /posts/
---

{% for post in site.posts %}
<div class="post-item">
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
</div>
{% endfor %}