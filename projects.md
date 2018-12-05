---
layout: page
title: Projects
permalink: /projects/
---
{% for project in site.projects%}
{% if project.draft == false %}

  

  <h2>
      <a href="{{ project.url }}">
        <div>
        <img src="{{project.image}}" style="max-width:300px;max-height:200px;" >  
        </div>
        <div>
        {{ project.title }}
        </div>
        
      </a>
  </h2>
  <p>{{ project.type }}</p>
  {% endif %}
{% endfor %}
