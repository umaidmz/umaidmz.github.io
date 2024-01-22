---
layout: default
permalink: /
---

{% include landing.html %}

<div style="margin-left: 2in;">
    ___
  <h4>Recent Posts</h4>
    {% for post in site.posts limit:5 %}
    ___     
    > <a href="{{ post.url | prepend: site.baseurl }}">{{ post.date | date_to_long_string }}: {{ post.title }}</a><br>
    {% endfor %}
    ___
</div>

