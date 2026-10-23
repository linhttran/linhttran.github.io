---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
redirect_from:
  - /publications/
---

{% if site.author.googlescholar %}
  You can also find my articles on <u><a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign published = site.publications | where_exp: "post", "post.status != 'wip'" | reverse %}
{% assign wip = site.publications | where_exp: "post", "post.status == 'wip'" | reverse %}

{% if published.size > 0 %}
<h2 class="archive__subtitle">Publications</h2>
{% for post in published %}
  {% include research-item.html %}
{% endfor %}
{% endif %}

{% if wip.size > 0 %}
<h2 class="archive__subtitle">Works in Progress</h2>
{% for post in wip %}
  {% include research-item.html %}
{% endfor %}
{% endif %}
