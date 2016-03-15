---
layout: archive
title: "Buildit Projects"
excerpt: "All Projects"
---

<div class="tiles">
{% for project in site.data.projects %}
  {% include project-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
