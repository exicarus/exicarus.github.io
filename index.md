---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="container">
    <div class="row gy-5">
        {% for post in site.posts %}
                    <div class="col-sm-4"> 
                        <a data-toggle="modal" data-target="#cardModal" data-title="{{ post.title }}" data-image="{{ post.image }}" alt="{{ post.title }}">
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
    <div class="modal fade" id="cardModal" tabindex="-1" role="dialog" aria-labelledby="cardModalLabel" aria-hidden="true">
    <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-body">
                <img class="card-img-top" src="" alt="{{ post.title }}">
                <div class="card-body text-center">
                    <div class="card-title"></div>
                </div>
            </div>
        </div>
    </div>
</div>
</div>
<script>
    $('#cardModal').on('show.bs.modal', function (event) {
    var button = $(event.relatedTarget);
    var title = button.data('title');
    var image = button.data('image');
    var modal = $(this)
    modal.find('.card-img-top').attr('src', image);
    modal.find('.card-title').html(title);

    });
</script>