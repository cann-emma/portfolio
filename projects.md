---
layout: default
title: Projects
---

{% assign sorted_projects = site.projects | sort: "order" %}
{% assign categories = sorted_projects | map: "category" | uniq %}

{% for category in categories %}
  <h2>{{ category }}</h2>
  <div class="project-grid">

    {% for project in sorted_projects %}
      {% if project.category == category %}
        <div class="project-card">
          {% if project.image %}
            <img src="{{ project.image }}" alt="{{ project.title }}">
          {% endif %}
          <h3>
            <a href="{{ project.url }}">{{ project.title }}</a>
          </h3>
          <p>{{ project.description }}</p>
        </div>
      {% endif %}
    {% endfor %}

  </div>
{% endfor %}
