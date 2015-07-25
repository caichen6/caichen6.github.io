---
layout: archive
title: "Life Archive:"
image: 
    feature: life.jpg
    teaser: life
---

<div class="tiles">
{% for post in site.categories.life %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
