---
layout: page
permalink: /students/
title: Students
description: Students and Alumni
nav: true
nav_order: 3
horizontal: false
---
<div class="students">

<!-- Display projects without categories -->
  {%- assign sorted_students = site.students | sort: "lastname" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for student in sorted_students -%}
      {% include students_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for student in sorted_students -%}
      {% include student.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
</div>
