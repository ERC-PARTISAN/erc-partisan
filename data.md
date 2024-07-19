---
title: Data
layout: page
description: data
permalink: "/data/"
bodyClass: page-about
intro_image_absolute: true
intro_image_hide_on_mobile: false
---

# Cross-sectional survey

<div class="surveys">
  {% for survey in site.data.data_survey %}
    <div class="survey">
      <h2>{{ survey.title }}</h2>
      {% if survey.status %}
        <p><strong>Status:</strong> {{ survey.status }}</p>
      {% endif %}
      <p>
        {% if survey.data_link %}
          <a href="{{ survey.data_link }}">Data</a>
        {% endif %}
        {% if survey.codebook_link %}
          {% if survey.data_link %}
            |
          {% endif %}
          <a href="{{ survey.codebook_link }}">Codebook</a>
        {% endif %}
        {% if survey.publication_link %}
          {% if survey.data_link or survey.codebook_link %}
            |
          {% endif %}
          <a href="{{ survey.publication_link }}">Publication</a>
        {% endif %}
        {% if survey.pre_registration_link %}
          {% if survey.data_link or survey.codebook_link or survey.publication_link %}
            |
          {% endif %}
          <a href="{{ survey.pre_registration_link }}">Pre-registration</a>
        {% endif %}
      </p>
    </div>
  {% endfor %}
</div>

<style>
  .surveys {
    margin-top: 20px;
  }
  .survey {
    margin-bottom: 20px;
  }
  .survey h2 {
    font-size: 1.5em;
  }
  .survey p {
    margin: 5px 0;
  }
  .survey a {
    text-decoration: none;
    color: #2a2939;
    text-decoration: underline;
  }
  .survey a:hover {
    text-decoration: underline;
  }
  .section-title {
    margin-top: 70px; /* Adjust the space above the section title as needed */
  }
</style>


<div class="section-title"></div>


# Survey experiments


<div class="surveys">
  {% for survey in site.data.data_experiments %}
    <div class="survey">
      <h2>{{ survey.title }}</h2>
      {% if survey.status %}
        <p><strong>Status:</strong> {{ survey.status }}</p>
      {% endif %}
      <p>
        {% if survey.data_link %}
          <a href="{{ survey.data_link }}">Data</a>
        {% endif %}
        {% if survey.codebook_link %}
          {% if survey.data_link %}
            |
          {% endif %}
          <a href="{{ survey.codebook_link }}">Codebook</a>
        {% endif %}
        {% if survey.publication_link %}
          {% if survey.data_link or survey.codebook_link %}
            |
          {% endif %}
          <a href="{{ survey.publication_link }}">Publication</a>
        {% endif %}
        {% if survey.pre_registration_link %}
          {% if survey.data_link or survey.codebook_link or survey.publication_link %}
            |
          {% endif %}
          <a href="{{ survey.pre_registration_link }}">Pre-registration</a>
        {% endif %}
      </p>
    </div>
  {% endfor %}
</div>
