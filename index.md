---
layout: default
---

<div class="container">
    <div class="row gy-5">
        {% for post in site.posts %}
                    <div class="col-sm-4"> 
                        <a data-toggle="modal" data-target="#cardModal" data-title="{{ post.title }}" data-image="{{ post.image }}"
                        data-french="{{ post.french }}" data-english="{{ post.english }}" data-vietnamese="{{ post.vietnamese }}" alt="{{ post.title }}">
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
                                   <img src="/assets/img/volume-up-fill.svg" />
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="card">
                              <ul class="list-group list-group-flush">
                                <li class="list-group-item"><img src="/assets/img/uk.png" class="rounded-circle mt-3 mx-auto img-thumbnail card-flag"/><span id="en"></span></li>
                                <li class="list-group-item"><img src="/assets/img/fr.png" class="rounded-circle mt-3 mx-auto img-thumbnail card-flag"/><span id="fr"></span></li>
                                <li class="list-group-item"><img src="/assets/img/vn.png" class="rounded-circle mt-3 mx-auto img-thumbnail card-flag"/><span id="vn"></span></li>
                            </ul>
                            <!-- <img src="/assets/img/fr.png" class="rounded-circle mt-3 mx-auto img-thumbnail card-flag"/>
                            <div id="fr"></div> -->
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
    var english = button.data('english');
    var french = button.data('french');
    var vietnamese = button.data('vietnamese');
    var modal = $(this)
    modal.find('.card-img-top').attr('src', image);
    modal.find('.card-img-top').attr('alt', title);
    modal.find('.card-title').html(title);
    modal.find('#en').html(english);
    modal.find('#fr').html(french);
    modal.find('#vn').html(vietnamese);
    });
</script>