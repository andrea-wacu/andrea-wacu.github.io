---
title: "Projects"
permalink: /projects/
layout: single
author_profile: true
---

Here you'll find a collection of my data analysis projects, showcasing my skills in data cleaning, exploratory analysis, and visualization.

{% for project in site.projects %}
  <article class="project-item" style="margin-bottom: 3rem; padding-bottom: 2rem; border-bottom: 1px solid #eee;">
    <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
    <p class="project-meta" style="color: #666; font-size: 0.9em; margin-bottom: 1rem;">
      <time datetime="{{ project.date | date_to_xmlschema }}">
        {{ project.date | date: "%B %d, %Y" }}
      </time>
      {% if project.categories %}
        in <span>{{ project.categories | join: ", " }}</span>
      {% endif %}
    </p>
    <p>{{ project.excerpt }}</p>
    <p><a href="{{ project.url }}" class="btn btn--primary">Read More</a></p>
  </article>
{% endfor %}
