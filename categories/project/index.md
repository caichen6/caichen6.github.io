---
layout: archive
title: "Latest Posts in *Project*"
excerpt: "Documents of my projects"

---

<div class="tiles">
{% for post in site.categories.project %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
