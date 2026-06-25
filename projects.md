---
layout: page
title: Projects
permalink: /projects/
---

# Projects

This page lists projects by year. Each item links to a dedicated detail page that can be expanded over time.

{% assign year_groups = site.projects | sort: "year" | reverse | group_by: "year" %}
{% for group in year_groups %}
## {{ group.name }}

{% assign projects = group.items | sort: "title" %}
{% for project in projects %}
### [{{ project.title }}]({{ project.url | relative_url }})

{{ project.summary }}

{% if project.stack %}
Tech: {{ project.stack | join: ", " }}
{% endif %}

{% endfor %}
{% endfor %}
