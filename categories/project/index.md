---
layout: archive
title: "Project Archive:"
image: 
    feature: project.jpg
    teaser: project
---

<div class="tiles">
{% for post in site.categories.project %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
