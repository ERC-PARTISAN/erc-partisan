---
title: Publications
layout: page
description: Publication page
permalink: "/publications/"
bodyClass: page-about
intro_image_absolute: true
intro_image_hide_on_mobile: false
---

<style>
  .publication {
    margin-bottom: 40px; /* Adjust the space between publications as needed */
  }
  .publication h2 {
    font-size: 1.5em;
  }
  .publication p {
    margin: 5px 0;
  }

   .toggle-button {
    background-color: transparent;
    border: 1px solid #2a2939;
    color: #2a2939;
    padding: 5px 10px;
    font-size: 1em;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s, color 0.3s;
  }

  .toggle-button:hover {
    background-color: #2a2939;
    color: #fff;
  }

  .toggle-button:focus {
    outline: none;
  }

  .abstract {
    display: none;
  }
</style>






<div class="publications">
  {% for publication in site.data.publications %}
    <div class="publication">
      <h2>{{ publication.title }}</h2>
      <p>
        <button class="toggle-button" onclick="toggleAbstract('abstract-{{ forloop.index }}')">Abstract</button>
      </p>
      <p id="abstract-{{ forloop.index }}" class="abstract">
        {{ publication.abstract }}
      </p>
      <p>
        {% if publication.publication_link %}
          <a href="{{ publication.publication_link }}">Publication</a>
        {% endif %}
        {% if publication.pre_registration_link %}
          {% if publication.publication_link %}
            |
          {% endif %}
          <a href="{{ publication.pre_registration_link }}">Pre-registration</a>
        {% endif %}
      </p>
    </div>
  {% endfor %}
</div>




<script>
  function toggleAbstract(id) {
    var abstract = document.getElementById(id);
    if (abstract.style.display === "none") {
      abstract.style.display = "block";
    } else {
      abstract.style.display = "none";
    }
  }
</script>


