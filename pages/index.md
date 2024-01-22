---
layout: default
permalink: /
---


{% include landing.html %}



<div style="margin-top: 2in; margin-right: 2in; margin-left: 2in;">
  <h4>Recent Posts</h4>
  {% for post in site.posts limit:5 %}
    <hr>
    <a href="{{ post.url | prepend: site.baseurl }}">
      <blockquote>
        {{ post.date | date_to_long_string }}: {{ post.title }}
      </blockquote>
    </a>
  {% endfor %}
  <hr>
</div>




