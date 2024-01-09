---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="container-md">
    <div class="row align-items-center">
    {% for post in site.posts %}
                <div class="col-md-4"> 
                    <a href="{{ post.url }}">
                        <div class="card" style="width: 18rem;">
                            <img class="card-img-top" src="{{ post.image }}" alt="Card image cap">
                            <div class="card-body">
                                <h5 class="card-title">{{ post.title }}</h5>
                            </div>
                        </div>
                    </a>
                </div>
    {% endfor %}
    </div>
</div>