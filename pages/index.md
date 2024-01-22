---
layout: default
permalink: /
---


{% include landing.html %}



<div style="margin-top: 2in; margin-right: 2in; margin-left: 2in;">
  <h4>Recent Posts</h4>
  {% for post in site.posts limit:5 %}
    <hr>
    <ul>
        <li>
        <a href="{{ post.url | prepend: site.baseurl }}">
         {{ post.title }}</a>
        </li>
{% endfor %}
  <hr>
</div>




