---
layout: page
title: Publications
sidebar_link: true
sidebar_sort_order: 3
---


{% assign pub_types = "paper,blogpost,student_thesis,doctoral_thesis,book,other"  | split:',' %}

{% for project in site.data.publications.projects %}

{% if project.id == "other" %}
## Other Related Work
{% else %}
## Work Related to the Project "{{ project.title }}"
{% endif %}


{% for pub_type in pub_types %}

{% assign works = site.data.publications.publications | where:"type", pub_type | where:"project", project.id %}

{% if works != empty %}

{% case pub_type %}
{% when "paper" %}
### Papers
{% when "blogpost" %}
### Blogposts
{% when "student_thesis" or "doctoral_thesis" %}
### Theses
{% when "book" %}
### Books & Edited Volumes
{% when "other" %}
### Other
{% endcase %}


{% for work in works %}

{% if work.link or work.internal_link or  work.download_link %}
{% assign linked = true %}
{% else %}
{% assign linked = false %}
{% endif %}



+ {{ work.citation }} {% if linked %} [ {% endif %} {% if work.abstract %} 👉 <a href="{{ '/publications.html#' | append: work.header_id | relative_url }}">details</a> {% elsif work.link %}👉 <a href="{{ work.link }}" target="_blank">external link</a> {% elsif work.internal_link %}👉 <a href="{{ work.internal_link | relative_url }}" target="_blank">link</a> {% endif %}  {% if work.download_link %} , 📥 <a href="{{ work.download_link }}" target="_blank">download</a>{% endif %} {% if linked %} ] {% endif %}

{% endfor %}

{% endif %}

{% endfor %} <!-- end looping through pubtypes -->

{% endfor %} <!-- end looping through projects -->





## Details

{% for work in site.data.publications.publications %}



{% if work.abstract %}

### {{ work.title }} {% if work.header_id %} {#{{ work.header_id }}} {% endif %}

{{ work.citation }} [{% if work.link %} 👉 <a href="{{work.link }}" target="_blank">external link</a> {% endif %} {% if work.download_link %} , 📥 <a href="{{ work.download_link }}" target="_blank">download</a>{% endif %}]


*Abstract*

{{ work.abstract }}

{% endif %}

{% endfor %}


