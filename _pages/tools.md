---
layout: archive

permalink: /tools/

title: "All Tools"
author_profile: true
---

{% assign grouped = site.studies | group_by: "group" %}

{% capture written_label %}None{% endcapture %}

{% for group in grouped %}
{% assign label = group.name | default: "uncategorized" %}

{% if label != written_label %}
<h2 id="{{ label | slugify }}" class="archive__subtitle">{{ label }}</h2>
{% capture written_label %}{{ label }}{% endcapture %}
{% endif %}

{% assign posts = group.items | sort: "date" | reverse %}

{% for post in posts %}
{% include archive-single.html type=page.entries_layout %}
{% endfor %}
{% endfor %}
