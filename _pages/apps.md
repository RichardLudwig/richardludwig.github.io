---
title: "Apps"
layout: default
permalink: "/apps"
---

<div class="container">
    <div class="row justify-content-center">
        <div class="col-md-8">
        <h1 class="font-weight-bold title h6 text-uppercase mb-4">Apps</h1>
            
        {% for post in site.tags.apps %}
          {% if post.title != null %}
            {% if group == null or group == post.group %}
          
              {% include main-loop-card.html %}
            {% endif %}
          {% endif %}
        {% endfor %}
      <p>Coming soon.</p>
      </div>
      <div class="col-md-4">
        {% include sidebar-featured.html %}    
      </div>
    </div>
</div>