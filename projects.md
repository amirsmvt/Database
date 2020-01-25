---
layout: page
title: Projects
permalink: /projects/
---


<ul id="archive">
{% for project in site.projects reversed %}
<li class="archiveposturl" style="background: transparent">
<div class="project-container">
    {% if project.thumbnail %}
    <div class="thumbnail">
      <div class="center-cropped" style="margin-top:5px;margin-bottom:5px;background-image: url('{{ project.thumbnail | prepend: site.baseurl }}');">
        <img src="{{ project.thumbnail | prepend: site.baseurl }}"/>
      </div>
    </div>
    {% endif %}
    <div class="content">
        <span><a href="
            {% if project.slides contains '://' %}
              {{ project.slides }} 
            {% else %}
              {{ project.slides | prepend: site.baseurl }} 
            {% endif %}">{{ project.title }}</a>
        </span><br>

        {% if project.tldr %}
            <strong>tl;dr:</strong> 
            {{ project.tldr }}
            <br/>
        {% endif %}

        <strong>
            {% include project_links.html project=project %}
        </strong>
    </div>
</div>
</li>
{% endfor %}
</ul>