---
layout: page
title: Projects
permalink: /projects/
---

<div style="display: flex; flex-wrap: wrap; justify-content: flex-start; align-items: flex-start; align-content: flex-start;">


{% for project in site.projects%}
{% if project.draft == false %}

  <div style="display: flex; flex-wrap: wrap; flex-direction:column; padding:20px;" >
      <a href="{{ project.url }}">
        <div style="">
        <img src="{{project.image}}" style="max-width:300px;max-height:200px;" >  
        </div>
        <div>
        {{ project.title }}
        </div>
        
      </a>
  
  <p>{{ project.type }}</p>
  </div>
  {% endif %}
{% endfor %}

</div>