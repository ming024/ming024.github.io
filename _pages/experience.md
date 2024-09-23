---
layout: page
permalink: /experience/
title: experience
description: Highlights of my education & research experience, honors received, and academic talks I gave. Please find my <a href='/assets/pdf/Chung_Ming_Chien_CV_20240923.pdf'>CV</a> for more information.
nav: true
nav_order: 2
display_categories: [education, research, honors, service, talks]
horizontal: false
---

<!-- pages/experience.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized experience -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_experience = site.projects | where: "category", category -%}
  {%- assign sorted_experience = categorized_experience | sort: "importance" %}
  <!-- Generate cards for each experience -->
  {%- for entry in sorted_experience -%}
    <div class="card mt-3 p-3">
      <h4 class="card-title font-weight-medium">{{ entry.title }}</h4>
        <div>
          {% if entry.type == "list" %}
          {% include cv/list.html %}
          {% elsif entry.type == "map" %}
          {% include cv/map.html %}
          {% elsif entry.type == "nested_list" %}
          {% include cv/nested_list.html %}
          {% elsif entry.type == "time_table" %}
          {% include cv/time_table.html %}
          {% else %}
          {{ entry.contents }}
          {% endif %}
        </div>
    </div>
  {%- endfor %}
  {%- endfor %}
{%- endif -%}
</div>
