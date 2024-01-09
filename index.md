---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<ul>
  {% for post in site.posts %}
    <li>
<div class="card" style="width: 18rem;">
  <img class="card-img-top" src="{{ post.image }}" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{ post.title }}</h5>
    <a href="{{ post.url }}" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    </li>
  {% endfor %}
</ul>