---
layout: events
title: Gallery
subtitle: null
banner_image: /assets/images/cover_picture.png
permalink: /gallery/

gallery_images:
  - file: open_house_feb26.jpg
    caption: "AIDE Lab showcased at biosystems Engineering open house event"
    href: null
  - file: gokarna_mac2025.jpg # image file name stored in assets/images/gallery/
    caption: "Gokarna presenting at the Manitoba Agronomists' Conference (MAC) 2025"
    href: /newsfeed/dec10-2025/ # link if this image associated with any events (eg. /newsfeed/dec10-2025/)
  - file: stephane_bioe_acm2025.jpg
    caption: "Stephane presenting at Biosystems Engineering ACM 2025"
    href: null
  - file: drone_setup_point_jun2125.jpg
    caption: "Setting up drone for data collection at Point"
    href: null
  - file: mobile_robot_datacollection_jul1025.jpg
    caption: "Mobile robot collecting data in the field"
    href: null
---

<!-- Content here would show up in body -->
<div class="row">
{% for item in page.gallery_images %}
  <div class="col-sm-6 col-md-4 mb-4">
    <div class="card h-100 mb-0">
      <!-- <img src="{{ site.baseurl }}/assets/images/gallery/{{ item.file }}" class="card-img" alt="{{ item.caption }}"> -->
      <!-- if any image has the href beside the caption then add anchor tag for href -->
      <img src="{{ site.baseurl }}/assets/images/gallery/{{ item.file }}" 
           class="card-img gallery-img" 
           alt="{{ item.caption }}"
           data-full="{{ site.baseurl }}/assets/images/gallery/{{ item.file }}"
           style="height: 250px; object-fit: contain; width: 100%; background-color: #f8f9fa;">
      <div class="card-body-bottom p-3">
        <p class="card-text text-center text-muted m-0 small">
        {{ item.caption }}
        {% if item.href != nil %}
        <a href="{{item.href}}" class="small"> &nbsp; More info</a>
        {% endif %}
        </p>
      </div>
    </div>
  </div>
{% endfor %}
</div>

<!-- Lightbox Modal -->
<div id="lightbox" style="
  display:none;
  position:fixed;
  top:0; left:0;
  width:100%; height:100%;
  background:rgba(0,0,0,0.85);
  z-index:1050;
  justify-content:center;
  align-items:center;">
  <img id="lightbox-img" style="max-width:80%; max-height:80%;">
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const lightbox = document.getElementById("lightbox");
  const lightboxImg = document.getElementById("lightbox-img");

  document.querySelectorAll(".gallery-img").forEach(img => {
    img.addEventListener("click", function () {
      lightboxImg.src = this.dataset.full;
      lightbox.style.display = "flex";
    });
  });

  lightbox.addEventListener("click", () => {
    lightbox.style.display = "none";
  });

  document.addEventListener("keydown", (e) => {
    if (e.key === "Escape") {
      lightbox.style.display = "none";
    }
  });
});
</script>
