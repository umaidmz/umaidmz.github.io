---
layout: default
permalink: /
---
<style>
.blockquote-link {
  display: block;
  text-decoration: none; 
  color: inherit;
  transition: background-color 0.3s;
}

.blockquote-link:hover {
  background-color: #f0f0f0; /* light grey background */
}
</style>

{% include landing.html %}



<div style="margin-top: 3in; margin-right: 2in; margin-left: 2in;">
  <h4>Recent Posts</h4>
  {% for post in site.posts limit:5 %}
    <hr>
    <a href="{{ post.url | prepend: site.baseurl }}" class="blockquote-link">
      <blockquote style="margin: 0;">
        {{ post.date | date_to_long_string }}: {{ post.title }}
      </blockquote>
    </a>
  {% endfor %}
  <hr>
</div>




