---
layout: default
permalink: /
---

{% include landing.html %}

<div style="margin-left: 2in;">
  <h3>Recent Posts</h3>
  <ul>
    {% for post in site.posts limit:5 %}
      <li>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
</div>