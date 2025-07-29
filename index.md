---
title: Online gehostete Anweisungen
permalink: index.html
layout: home
---

# Inhaltsverzeichnis

Hyperlinks zu den Lab-Übungen und Demos sind nachfolgend aufgelistet.

> **Hinweis:** Wenn Fehler mit dem Inhalt auftreten, erstellen Sie [ein neues Problem im GitHub-Repository](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/issues/new/choose).

## Labübungen

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Modul | Lab |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} – {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## Demos

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}

| Demo |
| --- |
{% for activity in demos  %}| [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
