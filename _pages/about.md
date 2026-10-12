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
  <li><strong>Machine Learning for Health:</strong> Building and comparing models that predict disease risk from patient records, with attention to class imbalance and honest evaluation (AUROC, AUPRC).</li>
  <li><strong>Computational Biology:</strong> Working with real genome data on high-performance computing clusters, from sequence alignment and variant calling to linking a mutation to the disease it causes.</li>
  <li><strong>Clinical Trial Technology:</strong> Using AI to pull study designs out of trial protocols and check them against industry data standards, so trials spend less time on manual reconciliation.</li>
  <li><strong>Computer Science Education:</strong> Running The Compute Initiative, which gives students in rural Indian schools daily time at a computer and a path into coding.</li>
</ul>

{% if portfolio_items and portfolio_items.size > 0 %}
## Featured work
<p>Current work includes:</p>
<ul>
{% for item in portfolio_items %}
  <li><strong>{% if item.url != "" %}<a href="{{ item.url }}">{{ item.name }}</a>{% else %}{{ item.name }}{% endif %}</strong> · {{ item.category }}{% if item.date %}, {{ item.date | date: "%Y" }}{% endif %}. {{ item.description }}</li>
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

## Connect
<ul>
  {% if author.website %}<li>Website: <a href="{{ author.website }}">{{ author.website }}</a></li>{% endif %}
  {% if author.email %}<li>Contact: <a href="mailto:{{ author.email }}">{{ author.email }}</a></li>{% endif %}
  {% if site.data['portfolio-data'].profiles %}
    {% for profile in site.data['portfolio-data'].profiles %}
      <li><a href="{{ profile.url }}">{{ profile.network }}</a></li>
    {% endfor %}
  {% endif %}
</ul>


