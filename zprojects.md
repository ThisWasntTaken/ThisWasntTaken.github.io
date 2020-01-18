---
layout: page
title: Projects
permalink: /projects/
---

{% for project in site.projects %}
  <div class="project">
      <h3>{{project.title}}</h3>
      {{ project.from }} - {{ project.to }}<br>
      {% if project.role %}
        <i>{{ project.role }}</i>
      {% endif %}
      <p>
          {{ project.content }}
      </p>
      <div id="links">
        {% if project.code %}
          <a target="_blank" rel="noopener noreferrer" href="{{project.code}}">Code</a>&nbsp;&nbsp;&nbsp;
        {% endif %}
        {% if project.report %}
          <a target="_blank" rel="noopener noreferrer" href="{{project.report}}">Report</a>&nbsp;&nbsp;&nbsp;
        {% endif %}
        {% if project.link %}
          <a target="_blank" rel="noopener noreferrer" href="{{project.link}}">Link</a>
        {% endif %}
      </div>
  </div>
{% endfor %}