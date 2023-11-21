---
layout: default
title: Prerequisites
---
{% include breadcrumb-2.html %}

<div class="container">
  <h1>Prerequisites <small class="header-small">Important material from other courses</small></h1>
</div>

{% if site.morea_overview_prerequisites %}
<div class="container">
 {{ site.morea_overview_prerequisites.content | markdownify }}
  <h2>The 5 Step Process</h2>

  1. <u>Understand the problem</u>
  <ul>
    <li>What is this program supposed to do?</li>
    <li>What kind of information is it given? (What is the input?)</li>
    <li>What kind of results is it to produce? (What is the output?)</li>
    <li>What formulas or techniques will be needed?</li>
  </ul>
2. <u>Do a small example by hand</u>
  <ul>
    <li>Create a small example(s) of what the program should do.</li>
    <li>Solve these examples and keep in mind the questions from step 1.</li>
  </ul>
3. <u>Write an algorithm for solving the problem</u>
  <ul>
    <li>Remember that each line of code is sequentially executed.</li>
    <li>Your algorithm must include all the steps sequentially to arrive at a solution.</li>
  </ul>
4. <u>Translate the algorithm into a programming language (like python, C, C++, Javascript, Java . . . etc.)</u><br>
<br>
5. <u>Test the program</u>
</div>
{% endif %}


{% for module in site.morea_module_pages %}
{% if module.morea_coming_soon != true and module.morea_prerequisites.size > 0 %}
<div class="{% cycle 'section-background-1', 'section-background-2' %}">
  <div class="container">
    <h2><small>Module:</small> <a href="{{ site.baseurl }}{{ module.module_page.url }}">{{ module.title }}</a></h2>
    <div class="row">
    {% for page_id in module.morea_prerequisites %}
      {% assign prereq = site.morea_page_table[page_id] %}
      {% include entity-card.html url=prereq.morea_url icon_url=prereq.morea_icon_url title=prereq.title summary=prereq.content labels=prereq.morea_labels %}
    {% endfor %}
    </div>
  </div>
</div>
{% endif %}
{% endfor %}
