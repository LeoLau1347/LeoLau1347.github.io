---
layout: archive

permalink: /studies/

title: "All Studies"
collection: studies
author_profile: true
---

{% assign docs = site.studies %}
{% assign grouped = site.studies | group_by: "field" %}

{% capture written_label %}None{% endcapture %}

{% for group in grouped %}
{% assign label = group.name | default: "uncategorized" %}

{% if label != written_label %}
<h2 id="{{ label | slugify }}" class="archive__subtitle">{{ label }}</h2>
{% capture written_label %}{{ label }}{% endcapture %}
{% endif %}

{% assign items = group.items | sort: "date" | reverse %}
{% for item in items %}
{% include archive-single.html post=item type=page.entries_layout %}
{% endfor %}
{% endfor %}
