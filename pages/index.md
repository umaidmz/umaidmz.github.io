---
layout: default
permalink: /
---

{% include landing.html %}

___
#### Recent Posts
{% for post in site.posts limit:5 %}
___     
> [{{ post.date | date_to_long_string }}: {{ post.title }}]({{ post.url | prepend: site.baseurl }})
{% endfor %}
___

