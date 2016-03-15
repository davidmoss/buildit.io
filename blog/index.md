---
layout: default
title: Blog
excerpt: "All Posts"
---

<div id="main" role="main">
  <div class="wrap">
    <h1>{{ page.title }}</h1>
    {% capture written_year %}'None'{% endcapture %}
    {% for post in site.categories.blog %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% if year != written_year %}
        <h3 class="post-year">{{ year }}</h3>
        {% capture written_year %}{{ year }}{% endcapture %}
      {% endif %}
      <article>
        {% if post.link %}
          <h4 class="link-post"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a> <a href="{{ post.link }}" target="_blank" title="{{ post.title }}"><i class="fa fa-link"></i></a></h4>
        {% else %}
          <h4><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h4>
          <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
        {% endif %}
      </article>
    {% endfor %}
  </div><!-- /#wrap -->
</div><!-- /#main -->
