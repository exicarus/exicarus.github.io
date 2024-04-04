---
layout: princess
---

{% assign posts = site.posts | where_exp: "item", "item.category contains 'princess'" %}

<div class="container">
    <div class="row gy-5 d-print-none">
        {% for post in posts %}
                    <div class="col-sm-4"> 
                        <a data-toggle="modal" data-target="#cardModal" data-title="{{ post.title }}" data-image="{{ post.image }}"
                        data-french="{{ post.french }}" data-english="{{ post.english }}" data-vietnamese="{{ post.vietnamese }}" alt="{{ post.title }}">
                            <div class="card-list">
                                <img class="card-img-top rounded-img" src="{{ post.image }}" alt="{{ post.title }}" />
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
                        <div class="card" id="img-modal">
                            <div class="card-body">
                                <img class="card-img-top" src="" alt=""  />
                                <div class="card-body text-center d-print-none">
                                    <div class="card-title "></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="card" id="label-modal">
                              <ul class="list-group list-group-flush">
                                <li class="list-group-item"><img src="/assets/flags/uk.png" class="rounded-circle mx-auto card-flag"/>&nbsp;<span class="align-middle" id="en"></span></li>
                                <li class="list-group-item"><img src="/assets/flags/fr.png" class="rounded-circle mx-auto card-flag"/>&nbsp;<span class="align-middle" id="fr"></span></li>
                                <li class="list-group-item"><img src="/assets/flags/vn.png" class="rounded-circle mx-auto card-flag"/>&nbsp;<span class="align-middle" id="vn"></span></li>
                            </ul>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="card d-print-none">
                            <div class="card-body">
                                <div class="card-body text-center">
                                   <img src="/assets/img/printer.png" id="printer" />
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
        var english = button.data('english');
        var french = button.data('french');
        var vietnamese = button.data('vietnamese');
        var modal = $(this)
        modal.find('.card-img-top').attr('src', image);
        modal.find('.card-img-top').attr('alt', title);
        modal.find('.card-title').html(french);
        modal.find('#en').html(english);
        modal.find('#fr').html(french);
        modal.find('#vn').html(vietnamese);
    });

    $('#printer').on('click', function (event) {
        window.print();
    });
</script>
