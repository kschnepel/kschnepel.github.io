---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}


### Work in Progress

* ``Paid too soon: Monthly assistance payments and crime in Vancouver'', with Hamza Abdelrahman 


{% include base_path %}

{% for post in site.research reversed %}
  {% include archive-single.html %}
{% endfor %}
