---
title: Work in Progress
layout: page
description: Work-in-Progress page
permalink: "/work-in-progress/"
bodyClass: page-about
intro_image_absolute: true
intro_image_hide_on_mobile: false
---

<style>
  .work-in-progress {
    margin-bottom: 40px; /* Same bottom margin as publications */
  }
  .work-in-progress h2 {
    font-size: 1.5em;
  }
  .work-item {
    margin-bottom: 40px; /* Set margin bottom for each work item */
  }
  .work-in-progress .authors,
  .toggle-button,
  .link-button {
    font-size: 0.9em;
    color: #555;
    margin-bottom: 10px;
  }
  .work-in-progress p {
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
    margin-right: 10px; /* Space between buttons */
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

<div class="work-in-progress">
  {% for work in site.data.workinprogress %}
    <div class="work-item"> <!-- Added class for individual work items -->
      <p class="citation">
        {% assign authors_count = work.authors | size %}
        {% for author in work.authors %}
          {% if forloop.last and authors_count > 1 %}
            & {{ author }}
          {% elsif forloop.index == authors_count - 1 %}
            {{ author }}
          {% else %}
            {{ author }}{% if forloop.last == false %}, {% endif %}
          {% endif %}
        {% endfor %} <i>{{ work.title }}</i>
      </p>
      <p>
        <button class="toggle-button" onclick="toggleAbstract('abstract-{{ forloop.index }}')">Abstract</button>
      </p>
      <p id="abstract-{{ forloop.index }}" class="abstract">
        {{ work.abstract }}
      </p>
      <p>
        {% if work.pre_registration_link %}
          <a class="link-button" href="{{ work.pre_registration_link }}">Pre-registration</a>
        {% endif %}
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
