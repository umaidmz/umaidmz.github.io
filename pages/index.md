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


{% capture list_items %}
<!-- {% for post in site.posts limit:5 %}
        {{post.date}}: {{ post.title }}, {{ post.url | prepend: site.baseurl }}
{% endfor %}-->
Google,https://www.google.com
GitHub,https://www.github.com
{% endcapture %} 

{% include elements/list.html title="Table of Contents" type="toc" size="sm"%}