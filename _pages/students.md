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
      {%- if student.current -%}
        {% include students_horizontal.html %}
      {%- endif -%}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for student in sorted_students -%}
      {%- if student.current -%}
        {% include student.html %}
      {%- endif -%}
    {%- endfor %}
  </div>
  {%- endif -%}
  <h2>PAST STUDENTS</h2>
  <br>
  {%- include past_students.html %}
  <br>
</div>
