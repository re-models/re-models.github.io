---
layout: page
title: Publications
sidebar_link: true
sidebar_sort_order: 3
---

{% assign project_internal_papers = site.data.publications.publications | where:"type", "paper" | where:"project_internal", true %}
{% assign project_internal_blogposts = site.data.publications.publications | where:"type", "blogpost" | where:"project_internal", true %}
{% assign project_internal_student_theses = site.data.publications.publications | where:"type", "student_thesis" | where:"project_internal", true %}
{% assign project_internal_doctoral_theses = site.data.publications.publications | where:"type", "doctoral_thesis" | where:"project_internal", true %}
{% assign project_internal_other = site.data.publications.publications | where:"type", "other" | where:"project_internal", true %}

{% assign project_external_work = site.data.publications.publications | where:"project_internal", false %}



## Project Internal Work

{% if project_internal_papers != empty %}
**Papers**

{% for paper in project_internal_papers %}
+ {{ paper.citation }} (👉 [<a href="{{ '/publications.html#' | append: paper.header_id | relative_url }}">details</a>])
{% endfor %}
{% endif %}

{% if project_internal_blogposts != empty %}
### Blogposts

{% for work in project_internal_blogposts %}
+ {{ work.citation }} (👉 [<a href="{{ work.link }}" target="_blank">external link</a>])
{% endfor %}
{% endif %}

{% if project_internal_student_theses != empty %}
### Student Theses 

{% for work in project_internal_student_theses %}
+ {{ work.citation }} {% if work.link %}(👉 [<a href="{{ work.link }}" target="_blank">external link</a>]) {% elsif work.internal_link %}(👉 [<a href="{{ work.internal_link | relative_url }}" target="_blank">link</a>]) {% endif %}
{% endfor %}
{% endif %}

{% if project_internal_doctoral_theses != empty %}
### Doctoral Theses 

{% for work in project_internal_doctoral_theses %}
+ {{ work.citation }} {% if work.link %}(👉 [<a href="{{ work.link }}" target="_blank">external link</a>]) {% elsif work.internal_link %}(👉 [<a href="{{ work.internal_link | relative_url }}" target="_blank">link</a>]) {% endif %}
{% endfor %}
{% endif %}

{% if project_internal_other != empty %}
### Other 

{% for work in project_internal_other %}
+ {{ work.citation }} {% if work.link %}(👉 [<a href="{{ work.link }}" target="_blank">external link</a>]) {% elsif work.internal_link %}(👉 [<a href="{{ work.internal_link | relative_url }}" target="_blank">link</a>]) {% endif %}
{% endfor %}
{% endif %}

## Related Work

{% for work in project_external_work %}
+ {{ work.citation }} {% if work.abstract != empty %} (👉 [<a href="{{ '/publications.html#' | append: work.header_id | relative_url }}">details</a>]) {% elsif work.link %}(👉 [<a href="{{ work.link }}" target="_blank">link</a>]) {% elsif work.internal_link %}(👉 [<a href="{{ work.internal_link | relative_url }})" target="_blank">external link</a>] {% endif %}
{% endfor %}


## Details

{% for work in site.data.publications.publications %}


{% if work.abstract %}

### {{ work.title }} {% if work.header_id %} {#{{ work.header_id }}} {% endif %}

{{ work.citation }} {% if work.link %} 👉 [<a href="{{work.link }}" target="_blank">external link</a>] {% endif %}

*Abstract*

{{ work.abstract }}

{% endif %}

{% endfor %}





{% if site.data.publications.posts %}
### Blog Posts

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