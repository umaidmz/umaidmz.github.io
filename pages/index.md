---
layout: default
permalink: /
---

{% include landing.html %}

<div style="margin-left: 2in;">
    ---
  <h4>Recent Posts</h4>
    {% for post in site.posts limit:5 %}
    ---
      
    > <a href="{{ post.url | prepend: site.baseurl }}">{{ post.date | date_to_long_string }}: {{ post.title }}</a>
      
    {% endfor %}
    ---
</div>
