---
layout: archive
title: "Latest Posts in *Book*"
excerpt: "Reading Notes of books I read"

---

<div class="tiles">
{% for post in site.categories.book %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
