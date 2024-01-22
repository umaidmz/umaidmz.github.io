---
layout: default
permalink: /
---


{% include landing.html %}



<div style="margin-top: 2in; margin-right: 2in; margin-left: 2in;">
  <h4>Recent Posts</h4>
   <ul>
  {% for post in site.posts limit:5 %}
  <a href="{{ post.url | prepend: site.baseurl }}">
    <hr>
   
        <li>{{ post.title }}</li> 
   </a>
{% endfor %}
 </ul>
  <hr>
</div>




