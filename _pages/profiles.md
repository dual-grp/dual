---
layout: page
permalink: /people/
title: people
description: members of the DUAL Group
nav: true
nav_order: 3
---

Our diverse team brings together researchers, students, and collaborators working across federated learning, distributed optimization, edge intelligence, and large language models.

{% assign role_groups = "professor:Lab Director|phd:PhD|mphil:MPhil|research-pathway:Research Pathway|honours:Honours|alumni:Alumni" | split: "|" %}

{% for role_group in role_groups %}
  {% assign role_parts = role_group | split: ":" %}
  {% assign role_key = role_parts[0] %}
  {% assign role_label = role_parts[1] %}
  {% assign members = site.members | where: "role", role_key | sort: "name" %}
  {% if members.size > 0 %}
## {{ role_label }}

<div class="row row-cols-1 row-cols-md-3 g-4 mb-4">
  {% for member in members %}
    <div class="col mb-4">
      <div class="card h-100">
        {% if member.image %}
          <a href="{{ member.url | relative_url }}">
            <img class="card-img-top" src="{{ member.image | relative_url }}" alt="{{ member.name }}" style="aspect-ratio: 1 / 1; object-fit: cover;">
          </a>
        {% endif %}
        <div class="card-body">
          <h5 class="card-title mb-1"><a href="{{ member.url | relative_url }}">{{ member.name }}</a></h5>
          {% if member.description %}
            <p class="card-text small mb-2">{{ member.description }}</p>
          {% endif %}
          {% include member_links.liquid links=member.links %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
  {% endif %}
{% endfor %}
