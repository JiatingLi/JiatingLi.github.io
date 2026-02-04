---
layout: base/default
title: Gallery
subtitle: null
banner_image: /assets/images/cover_picture.png
permalink: /gallery/

gallery_images:
  - file: gokarna_mac2025.jpg # image file name stored in assets/images/gallery/
    caption: "Gokarna presenting at MAC 2025"
    href: /newsfeed/dec10-2025/ # link if this image associated with any events (eg. /newsfeed/dec10-2025/)
  - file: drone_setup_point_jun2125.jpg # image file name stored in assets/images/gallery/
    caption: "Setting up drone for data collection"
    href: null # link if this image associated with any events (eg. /newsfeed/dec10-2025/)
---

<!-- Content here would show up in body -->
<div class="row">
{% for item in page.gallery_images %}
  <div class="col-sm-6 col-md-4 mb-4">
    <div class="card h-100 mb-0">
      <!-- <img src="{{ site.baseurl }}/assets/images/gallery/{{ item.file }}" class="card-img" alt="{{ item.caption }}"> -->
      <!-- if any image has the href beside the caption then add anchor tag for href -->
      {% if item.href != nil %}
      <a href="{{item.href}}">
      {% endif %}
      <img src="{{ site.baseurl }}/assets/images/gallery/{{ item.file }}" 
           class="card-img" 
           alt="{{ item.caption }}"
           style="height: 250px; object-fit: contain; width: 100%; background-color: #f8f9fa;">
      {% if item.href != nil %}
      </a>
      {% endif %}
      <div class="card-body-bottom p-3">
        <p class="card-text text-center text-muted m-0 small">{{ item.caption }}</p>
      </div>
    </div>
  </div>
{% endfor %}
</div>
