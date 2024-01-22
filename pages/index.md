---
layout: default
permalink: /
---

{% include landing.html %}

<div style="margin-left: 2in;">
  <h4>Recent Posts</h4>
  {% for post in site.posts limit:5 %}
    <hr>
    <blockquote>
      {{ post.date | date_to_long_string }}: <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </blockquote>
  {% endfor %}
  <hr>
</div>

#### Recent Posts
{% for post in site.posts limit:5 %}
___     
> {{ post.date | date_to_long_string }}: [{{ post.title }}]({{ post.url | prepend: site.baseurl }})
{% endfor %}
___

