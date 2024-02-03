---
title: Online gehostete Anweisungen
permalink: index.html
layout: home
---

# Inhaltsverzeichnis

Hyperlinks zu den Lab-Übungen und Demos sind nachfolgend aufgelistet.

## Labs

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Kurs | Modul | Lab |
| --- |--- | --- | 
{% for activity in labs  %}| {{ activity.lab.course }} |{{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} – {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## Demos

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}
| Kurs | Modul | Demo |
| --- |--- | --- | 
{% for activity in demos  %}| {{ activity.demo.course }} |{{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
