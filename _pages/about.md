---
permalink: /
title: "About"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% assign author = site.data['portfolio-data'].author %}
{% assign portfolio_items = site.data['portfolio-data'].portfolio %}
{% assign publications = site.data['portfolio-data'].publications %}



## About me
<p>{{ author.summary }}</p>

### My interests and focus areas
<p>Most of my work sits where code meets biology and medicine. Right now that includes:</p>
<ul>
  <li><strong>Machine Learning for Health:</strong> Building models that estimate disease risk and evaluating them with metrics that hold up on imbalanced clinical data.</li>
  <li><strong>Computational Biology:</strong> Analyzing genomic data at scale to connect genetic variation with disease.</li>
  <li><strong>Clinical Research Technology:</strong> Applying AI to automate and standardize the data behind clinical trials.</li>
  <li><strong>Computer Science Education:</strong> Expanding access to computing for students in rural and underserved communities.</li>
</ul>

{% if portfolio_items and portfolio_items.size > 0 %}
## Featured work
<p>Details on each project are on the <a href="/portfolio/">Portfolio</a> page.</p>
<ul>
{% for item in portfolio_items %}
  <li>{% if item.url != "" %}<a href="{{ item.url }}">{{ item.name }}</a>{% else %}{{ item.name }}{% endif %}</li>
{% endfor %}
</ul>
{% endif %}

{% if publications and publications.size > 0 %}
## Research highlights
<ul>
{% for pub in publications %}
  <li><a href="{{ pub.website }}">{{ pub.title }}</a> · {{ pub.publisher }}{% if pub.release_date %}, {{ pub.release_date | date: "%Y" }}{% endif %}</li>
{% endfor %}
</ul>
{% endif %}


### How I work
<p>I work best on problems I can test against real data. I start by dissecting a problem into its parts and sequencing the work so each stage can be verified before the next begins. From there, I construct the solution, rigorously validate it for accuracy, and optimize it for performance until it holds up under conditions it was not designed for. I do not consider work finished until it survives outside scrutiny. I also value explaining complex systems clearly, because a solution only creates impact when others can evaluate, adopt, and build on it.</p>
