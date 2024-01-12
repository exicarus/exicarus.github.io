---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="container">
        <div class="row row-cols-1 row-cols-md-3 g-4">
        {% for post in site.posts %}
                    <div class="col"> 
                        <a href="{{ post.url }}" alt="{{ mod }}">
                            <div class="card" style="width: 18rem;">
                                <img class="card-img-top" src="{{ post.image }}" alt="{{ post.title }}">
                                <div class="card-body text-center">
                                    <div class="card-title">{{ post.title }}</div>
                                </div>
                            </div>
                        </a>
                    </div>
        {% endfor %}
        </div>
</div>