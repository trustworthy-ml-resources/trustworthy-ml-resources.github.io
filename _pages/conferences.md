---
layout: page
permalink: /conferences/
title: conferences
description: trustworthy ml resources from conferences
nav: true
order: 5
---
<!--Here, we will create multiple folders for conferences. -->
Top tier machine learning conferences get larger every year and the number of accepted papers rises. This includes a lot of interesting papers from our community. Here, we would like to collect trustworthy ml resources from large conferences to highlight contributions from our community!
* Add links to the resources before a conference to draw attention to trustworthy ML talks. In this way, we can increase interactions on conferences and promote work from our community.
* Add papers/talks after a conference to complete the list of trustworthy ml resources for the given conference. 

If a conference is coming up we will provide a separate form for each conference we are covering. 
<!-- _conferences/-->


<div class="conferences">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.conferences | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for conference in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include conferences.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.conferences | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for conference in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>