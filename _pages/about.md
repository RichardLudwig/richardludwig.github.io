---
title: "About"
layout: default
permalink: "/about"
---
<div class="container">
<div class="row justify-content-center">
    <div class="col-md-8">        
        <div class="row align-items-center mb-5">
            <div class="col-md-9">
                <h2 class="font-weight-bold">{{site.authors.richard.name}}</h2>
                <p>{{ site.authors.richard.bio }}</p>
                <p class="excerpt">{{ site.description }}</p>
            </div>
            <div class="col-md-3 text-right">
                <img alt="{{ site.authors.richard.name }}" src="{{site.baseurl}}{{ site.authors.richard.avatar }}" class="rounded-circle" height="100" width="100">
            </div>
        </div>
        <h4 class="font-weight-bold spanborder"><span>Posts by {{site.authors.richard.name}}</span></h4>
            {% assign posts = site.posts | where:"author","richard" %}
            {% for post in posts %}
            {% include main-loop-card.html %}
            {% endfor %}
    </div>
</div>
</div>