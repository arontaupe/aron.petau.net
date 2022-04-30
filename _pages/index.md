---
layout             : splash
permalink          : /
hidden             : true
header:
  overlay_color    : "#5e616c"
  overlay_image    : /assets/images/about_header.jpeg
  text_color: "#FF7300"

  actions:
    - label        : "<i class='fas fa-book-open'></i> Take me to the Content!"
      url          : "/portfolio/"
excerpt            : The place where you can catch up with my recent work and see what I am all about. 

feature_row:
  - image_path: /assets/images/aron_headshot.jpeg
    alt: "About Me"
    title: "About Me"
    excerpt: "Come and have a look at who I am"
    url: "/about/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /assets/images/tanzania_giraffe_landscape.jpg
    alt: "experience"
    title: "Prior experience"
    excerpt: "The boring and hard facts about my Career and Skills "
    url: "/cv/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /assets/images/water_grass.jpg
    alt: "Motivation"
    title: "What motivates me"
    excerpt: "Come and check out what is important to me and how my plans for the future look"
    url: "/motivation/"
    btn_class: "btn--primary"
    btn_label: "Learn more"      
---

{% include feature_row %}
