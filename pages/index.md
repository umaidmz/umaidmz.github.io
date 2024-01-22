---
layout: default
permalink: /
---

{% include landing.html %}

<div style="margin-top: 3in; margin-right: 2in; margin-left: 2in;">
  <h4>Recent Posts</h4>
  {% for post in site.posts limit:5 %}
    <hr>
    <a href="{{ post.url | prepend: site.baseurl }}" style="text-decoration: none; color: inherit;">
      <blockquote style="margin: 0;">
        {{ post.date | date_to_long_string }}: {{ post.title }}
      </blockquote>
    </a>
  {% endfor %}
  <hr>
</div>


#### Recent Posts
{% for post in site.posts limit:5 %}
___     
> {{ post.date | date_to_long_string }}: [{{ post.title }}]({{ post.url | prepend: site.baseurl }})
{% endfor %}
___

