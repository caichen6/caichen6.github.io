---
layout: archive
permalink: /
title: "Home"
image: 
    feature: cover.jpg
    credit: Taken3
---

<div class="tiles">
{% for post in site.posts %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->