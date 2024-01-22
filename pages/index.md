---
layout: default
permalink: /
---
<style>
.blockquote-link:hover blockquote {
  background-color: #f0f0f0; /* light grey background */
}
</style>

{% include landing.html %}



<div style="margin-top: 2in; margin-right: 2in; margin-left: 2in;">
  <h4>Recent Posts</h4>
  {% for post in site.posts limit:5 %}
  <div class="blockquote-link">
    <hr>
    <a href="{{ post.url | prepend: site.baseurl }}"  style="text-decoration: none; color: inherit;">
      <blockquote style="margin: 0; transition: background-color 0.3s;">
        {{ post.date | date_to_long_string }}: {{ post.title }}
      </blockquote>
    </a>
    </div>
  {% endfor %}
  <hr>
</div>




