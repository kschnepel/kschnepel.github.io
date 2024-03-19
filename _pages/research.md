---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}


### Works in Progress

* *"Does nothing stop a bullet like a job? The effects of income on crime"*, with Jens Ludwig (Review article requested for the *Annual Review of Criminology*
* *"Paid too soon: Monthly assistance payments and crime in Vancouver"*, with Hamza Abdelrahman
* *"Better Stealing Than Dealing? The Effects of Felony Theft Thresholds"*, with Steve Billings, Mike Makowsky and Adam Soliman 
* *"Drinking Water Contaminants and Infant Health"*, with Katie Grooms and Heather Royer
* *"Early life health investment and childhood development: Evidence from special care nursery assignment in Australia's Northern Territory"*, with Steve Guthridge and Stefanie Schurer

### Working Papers and Publications

{% include base_path %}

{% for post in site.research reversed %}
  {% include archive-single.html %}
{% endfor %}
