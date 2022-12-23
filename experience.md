---
layout: page
title: Experience
permalink: /experience/
---

{% for experience in site.experience %}
  <div class="experience">
    <h3>{{experience.title}}</h3>
    {% if experience.from and experience.to %}
      <i>{{ experience.from }} - {{ experience.to }}</i>
    {% endif %}
    <p>
        {{ experience.content }}
    </p>
  </div>
{% endfor %}