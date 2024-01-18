---
layout: default
---

<div class="container">
    <div class="row gy-5">
        {% for post in site.posts %}
                    <div class="col-sm-4"> 
                        <a data-toggle="modal" data-target="#cardModal" data-title="{{ post.title }}" data-image="{{ post.image }}" alt="{{ post.title }}">
                            <div class="card card-list">
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
                <div class="row">
                    <div class="col-sm-12">
                        <div class="card">
                            <div class="card-body">
                                <img class="card-img-top" src="" alt="">
                                <div class="card-body text-center">
                                    <div class="card-title"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="card">
                            <div class="card-body">
                                <div class="card-body text-center">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" fill="currentColor" class="bi bi-volume-up-fill" viewBox="0 0 16 16">
                                    <path d="M11.536 14.01A8.47 8.47 0 0 0 14.026 8a8.47 8.47 0 0 0-2.49-6.01l-.708.707A7.48 7.48 0 0 1 13.025 8c0 2.071-.84 3.946-2.197 5.303z"/>
                                    <path d="M10.121 12.596A6.48 6.48 0 0 0 12.025 8a6.48 6.48 0 0 0-1.904-4.596l-.707.707A5.48 5.48 0 0 1 11.025 8a5.48 5.48 0 0 1-1.61 3.89z"/>
                                    <path d="M8.707 11.182A4.5 4.5 0 0 0 10.025 8a4.5 4.5 0 0 0-1.318-3.182L8 5.525A3.5 3.5 0 0 1 9.025 8 3.5 3.5 0 0 1 8 10.475zM6.717 3.55A.5.5 0 0 1 7 4v8a.5.5 0 0 1-.812.39L3.825 10.5H1.5A.5.5 0 0 1 1 10V6a.5.5 0 0 1 .5-.5h2.325l2.363-1.89a.5.5 0 0 1 .529-.06"/>
                                    </svg>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="card">
                            <div class="card-body">
                                <div class="card-body text-center">
                                    lorem ipsum dolor
                                </div>
                            </div>
                        </div>
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
    modal.find('.card-img-top').attr('alt', title);
    modal.find('.card-title').html(title);
    });
</script>