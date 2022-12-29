---
title: Online gehostete Anweisungen
permalink: index.html
layout: home
---

# <a name="content-directory"></a>Inhaltsverzeichnis

Hyperlinks zu den Lab-Übungen und Demos sind nachfolgend aufgelistet.

## <a name="labs"></a>Labs

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| `Section` | Labor |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} – {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
