---
title: "LearnData Lab at SKKU - Publications"
layout: gridlay
excerpt: "LearnData Lab at SKKU -- Publications."
sitemap: false
permalink: /publications/
---


## (Selected) Publications


<!-- ## Group highlights
(For a full list see [below](#full-list)) -->
For a full list, please see my [CV](http://hogunpark.com/about/cv.pdf).
<br/>
\* means the (co-)corresponding authorship of the PI.
<br/>
\+ means the co-first authorship.
 <!-- or go to [Google Scholar](https://scholar.google.ch/citations?user=TqxYWZsAAAAJ), [ResearcherID](https://www.researcherid.com/rid/D-7763-2012)) -->


{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="33%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<!-- <p> &nbsp; </p>  -->


<!-- ## Selected List -->

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  {{ publi.authors }} <br /> <em>{{ publi.link.display }}</em> <br />
  <em>{{ publi.news1 }} </em>

{% endfor %}


