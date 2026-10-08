---
layout: custompage
title: Shot on iPhone
nav_order: 4
---

<div class="photography-container">
  <div id="photography-gallery" class="photography-gallery">
    <!-- Photos will be loaded dynamically -->
  </div>
</div>

<div id="photo-modal" class="photo-modal">
  <span class="close-modal">&times;</span>
  <img class="modal-content" id="modal-img">

  <div id="modal-caption">
    <p id="modal-location"></p>
  </div>
</div>
{% assign photo_files = site.static_files | where_exp:"f","f.path contains '/assets/images/photography'" %}
<script>
  const photos = [
  {% for f in photo_files %}
    {% assign meta = site.data.photos[f.name] %}
    {
        url: "{{ site.url }}{{ f.path }}",  // url: "{{ f.path | relative_url }}",
        location: "{{ meta.location }}"
    }{% unless forloop.last %},{% endunless %}
  {% endfor %}
  ];
</script>

<script src="{{ site.url }}/assets/js/photography.js"></script>
