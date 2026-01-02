---
layout: collection

permalink: /studies/

title: "All Studies"
collection: studies
author_profile: true
---

{% assign docs = site.studies | sort: "date" | reverse %}
{% for d in docs %}
- {{ d.title }}
{% endfor %}
