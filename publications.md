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
    margin-bottom: 40px;
  }
  .publication h2 {
    font-size: 1.5em;
  }
  .publication .authors,
  .publication .toggle-button,
  .publication .link-button {
    font-size: 0.9em;
    color: #555;
    margin-bottom: 10px;
  }
  .publication p {
    margin: 5px 0;
  }
  .toggle-button,
  .link-button {
    background-color: transparent;
    border: 1px solid #2a2939;
    color: #2a2939;
    padding: 5px 10px;
    font-size: 0.9em;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s, color 0.3s;
    margin-right: 10px;
    display: inline-block;
    text-decoration: none; /* Ensure no underline for links */
  }
  .toggle-button:hover,
  .link-button:hover {
    background-color: #2a2939;
    color: #fff;
  }
  .toggle-button:focus,
  .link-button:focus {
    outline: none;
  }
  .abstract {
    display: none;
  }
</style>

<div class="publications">
  {% for publication in site.data.publications %}
    <div class="publication">
      <p class="citation">
        {% assign authors_count = publication.authors | size %}
        {% for author in publication.authors %}
          {% if forloop.last and authors_count > 1 %}
            & {{ author }}
          {% elsif forloop.index == authors_count - 1 %}
            {{ author }}
          {% else %}
            {{ author }}{% if forloop.last == false %}, {% endif %}
          {% endif %}
        {% endfor %}
        ({{ publication.year }}). {{ publication.title }}. 
        <i>{{ publication.journal }}</i>
        {% if publication.volume %}, <i>{{ publication.volume }}</i>{% endif %}{% if publication.issue %}<i>({{ publication.issue }})</i>{% endif %}{% if publication.pages %}, {{ publication.pages }}{% endif %}{% if publication.volume or publication.issue or publication.pages %}.{% endif %}
      </p>
      <p>
        <button class="toggle-button" onclick="toggleAbstract('abstract-{{ forloop.index }}')">Abstract</button>
        {% if publication.publication_link %}
          <a href="{{ publication.publication_link }}" class="link-button">Publication</a>
        {% endif %}
      </p>
      <p id="abstract-{{ forloop.index }}" class="abstract">
        {{ publication.abstract }}
      </p>
    </div>
  {% endfor %}
</div>

<script>
  function toggleAbstract(id) {
    var abstract = document.getElementById(id);
    if (abstract.style.display === "none" || abstract.style.display === "") {
      abstract.style.display = "block";
    } else {
      abstract.style.display = "none";
    }
  }
</script>

