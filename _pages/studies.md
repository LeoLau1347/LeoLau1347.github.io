---
layout: collection

permalink: /studies/

title: "All Studies"
collection: studies
author_profile: true
---

{% assign studies = site.collections.studies.docs | sort: "date" %}
{% assign grouped = studies | group_by: "categories" %}

{% for group in grouped %}
## {{ group.name | capitalize }}

{% assign items = group.items | reverse %}
{% for item in items %}
- **{{ item.date | date: "%Y-%m-%d" }}**
  [{{ item.title }}]({{ item.url }})
{% endfor %}
{% endfor %}