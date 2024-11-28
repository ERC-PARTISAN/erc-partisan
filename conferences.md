---
title: Conferences & Workshops
layout: page
description: Conference page
permalink: "/conferences/"
bodyClass: page-about
intro_image_absolute: true
intro_image_hide_on_mobile: false
---

<div class="conferences">
  {% for conference_year in site.data.conferences %}
    <h2>{{ conference_year.year }}</h2>
    {% for conference in conference_year.conferences %}
      <h3>{{ conference.title }}</h3>
      <ul>
        {% for paper in conference.papers %}
          <li>
            {% assign authors_count = paper.authors | size %}
            {% for author in paper.authors %}
              {% if forloop.last and authors_count > 1 %}
                & {{ author }}
              {% elsif forloop.index == authors_count - 1 %}
                {{ author }}
              {% else %}
                {{ author }}, 
              {% endif %}
            {% endfor %}
            <em>{{ paper.title }}</em>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  {% endfor %}
</div>

<style>
  .conferences h2 {
    font-size: 1.8em; /* Adjust the size as needed */
    font-weight: bold;
    margin-top: 50px; /* Space above each conference year */
  }
  .conferences h3 {
    margin-top: 20px; /* Space above each conference title */
    font-weight: bold;
  }
  .conferences ul {
    margin-top: 10px; /* Space above the list of papers */
    margin-bottom: 20px; /* Space below each conference section */
  }
  .conferences li {
    margin-bottom: 5px; /* Space between each paper */
  }
</style>
