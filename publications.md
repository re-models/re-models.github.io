---
layout: page
title: Publications
sidebar_link: true
sidebar_sort_order: 2
---


{% for paper in site.data.publications.papers %}

### {{ paper.title }}
{% if paper.citation %}
{{ paper.citation }} {% if paper.link %} 👉 [<a href="{{ paper.link }}" target="_blank">link</a>] {% endif %}
{% endif %}

{% if paper.abstract %}
*Abstract*

{{ paper.abstract }}
{% endif %}

{% endfor %}


{% if site.data.publications.student_theses %}
## Selected Students' Theses 

{% for thesis in site.data.publications.student_theses %}

+ {{ thesis.citation }}

{% endfor %}
{% endif %}


{% if site.data.publications.posts %}
## Blog Posts

{% for post in site.data.publications.posts %}

+ {{ post.title }} ({{ post.date }}) 👉 [<a href="{{ post.link }}" target="_blank">link</a>] 

{% endfor %}
{% endif %}



{% if site.data.publications.other %}
## Other
{% for work in site.data.publications.other %}

+ {{ work.type }}: {{ work.title }} {% if work.link %}👉 [<a href="{{ work.link }}" target="_blank">link</a>] {% elsif work.internal_link %}👉 [<a href="{{ work.internal_link | relative_url }}" target="_blank">link</a>]  {% endif %}

{% endfor %}
{% endif %}