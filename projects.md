---
layout: default
title: Projects
permalink: /projects/
---

{% assign sorted_projects = site.projects | sort: "order" %}

{% for project in sorted_projects %}
  <div class="project-card">
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    <a href="{{ project.url }}">View Project →</a>
  </div>
{% endfor %}
