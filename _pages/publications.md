---
title: "LearnData Lab at SKKU - Publications"
layout: gridlay
excerpt: "LearnData Lab at SKKU -- Publications."
sitemap: false
permalink: /publications/
---


## (Selected) Publications

For a full list, please see my [CV](http://hogunpark.com/about/cv.pdf).
<br/>
\* means the (co-)corresponding authorship of the PI.
<br/>
\+ means the co-first authorship.

<style>
.pub-links {
  color: #333;
  font-weight: 400;
}
.pub-links a {
  color: #3B82F6;
  font-weight: 600;
}
.pub-links a:hover {
  color: #2563EB;
  text-decoration: underline;
}
.pub-links a[href=""] {
  color: #333;
  font-weight: 400;
  pointer-events: none;
  text-decoration: none;
}
</style>

{% assign grouped = site.data.publist | group_by: "year" | sort: "name" | reverse %}

{% for year_group in grouped %}
{% assign y = year_group.name | plus: 0 %}

{% if y > 2020 %}

### {{ year_group.name }}

<div style="border-left: 3px solid #00E5CC; padding-left: 16px; margin-bottom: 24px;">

{% for publi in year_group.items %}
<div style="margin-bottom: 16px;">
  <pubtit>{{ publi.title }}</pubtit><br />
  {{ publi.authors }} <br />
  <em>{{ publi.link.display }}</em>
  {% if publi.news1 %}<br /><span class="pub-links">{{ publi.news1 }}</span>{% endif %}
  {% if publi.news2 %}<br />{{ publi.news2 }}{% endif %}
</div>
{% endfor %}

</div>

{% endif %}
{% endfor %}

{% assign before_skku = "" | split: "" %}
{% for year_group in grouped %}
{% assign y = year_group.name | plus: 0 %}
{% if y <= 2020 %}
{% for publi in year_group.items %}
{% assign before_skku = before_skku | push: publi %}
{% endfor %}
{% endif %}
{% endfor %}

{% if before_skku.size > 0 %}

### Before SKKU

<div style="border-left: 3px solid #00E5CC; padding-left: 16px; margin-bottom: 24px;">

{% for publi in before_skku %}
<div style="margin-bottom: 16px;">
  <pubtit>{{ publi.title }}</pubtit><br />
  {{ publi.authors }} <br />
  <em>{{ publi.link.display }}</em>
  {% if publi.news1 %}<br /><span class="pub-links">{{ publi.news1 }}</span>{% endif %}
  {% if publi.news2 %}<br />{{ publi.news2 }}{% endif %}
</div>
{% endfor %}

</div>

{% endif %}
