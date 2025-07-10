---
layout: page
title: Team
permalink: /team/
description: 
nav: true
nav_order: 1
---

{%- assign featured_with_pic = site.data.team | where: "category", "feature" | where_exp: "item", "item.profilepic" | sort_natural: "lastname" -%}
{%- assign featured_without_pic = site.data.team | where: "category", "feature" | where_exp: "item", "item.profilepic == nil" | sort_natural: "lastname" -%}
{%- assign featured = featured_with_pic | concat: featured_without_pic -%}

{%- assign postdoc_with_pic = site.data.team | where: "category", "postdoc" | where_exp: "item", "item.profilepic" | sort_natural: "lastname" -%}
{%- assign postdoc_without_pic = site.data.team | where: "category", "postdoc" | where_exp: "item", "item.profilepic == nil" | sort_natural: "lastname" -%}
{%- assign postdoc = postdoc_with_pic | concat: postdoc_without_pic -%}

{%- assign phd_with_pic = site.data.team | where: "category", "phd" | where_exp: "item", "item.profilepic" | sort_natural: "lastname" -%}
{%- assign phd_without_pic = site.data.team | where: "category", "phd" | where_exp: "item", "item.profilepic == nil" | sort_natural: "lastname" -%}
{%- assign phd = phd_with_pic | concat: phd_without_pic -%}

{% assign engineer = site.data.team | where: "category", "engineer" | sort_natural: "lastname" %}
{% assign intern = site.data.team | where: "category", "intern" | sort_natural: "lastname" %}
{% assign alumni = site.data.team | where: "category", "alumni" | sort_natural: "lastname" %}

<!-- Featured Members -->
{% if featured.size > 0 %}
<h2 class="team-category-title">Permanent Members</h2>
<div class="team featured">
  {% for member in featured %}
    {% include team/member.html member=member %}
  {% endfor %}
</div>
{% endif %}

<!-- Add some vertical space -->
<div class="spacer"></div>

   

<!-- Postdocs -->
{% if postdoc.size > 0 %}
<h2 class="team-category-title">Postdocs</h2>
<div class="team postdoc">
  {% for member in postdoc %}
    {% include team/member.html member=member %}
  {% endfor %}
</div>
{% endif %}


<!-- PhD Students -->
{% if phd.size > 0 %}
<h2 class="team-category-title">PhD Students</h2>
<div class="team phd">
  {% for member in phd %}
    {% include team/member.html member=member %}
  {% endfor %}
</div>
{% endif %}

<!-- Engineer -->
{% if engineer.size > 0 %}
<h2 class="team-category-title">Engineer</h2>
<div class="team engineer">
  {% for member in engineer %}
    {% include team/member.html member=member %}
  {% endfor %}
</div>
{% endif %}

<!-- Interns -->
{% if intern.size > 0 %}
<h2 class="team-category-title">Interns</h2>
<div class="team intern">
  {% for member in intern %}
    {% include team/member.html member=member %}
  {% endfor %}
</div>
{% endif %}

<!-- Alumni -->
{% if alumni.size > 0 %}
<h2 class="team-category-title">Alumni</h2>
<div class="team alumni">
  {% for member in alumni %}
    {% include team/member.html member=member %}
  {% endfor %}
</div>
{% endif %}