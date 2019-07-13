---
layout: page
title: Education
permalink: /education/
---

{% for education in site.education %}
  <div class="education">
    <h3>{{education.title}}</h3>
    {% if education.from and education.to %}
      <i>{{ education.from }} - {{ education.to }}</i>
    {% endif %}
    <p>
        {{ education.content }}
    </p>
  </div>
{% endfor %}