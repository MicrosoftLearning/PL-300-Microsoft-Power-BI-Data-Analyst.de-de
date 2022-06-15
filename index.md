---
title: Online gehostete Anweisungen
permalink: index.html
layout: home
ms.openlocfilehash: 0c2c63aea8926ec06e02203a9ff9a9a5d5cc9b85
ms.sourcegitcommit: 9f66e4932aaf188d3be327646561dc7fe8e5c7a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2022
ms.locfileid: "143996839"
---
# <a name="content-directory"></a>Inhaltsverzeichnis

Hyperlinks zu den Lab-Übungen und Demos sind nachfolgend aufgelistet.

## <a name="labs"></a>Labs

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Modul | Labor |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} – {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
