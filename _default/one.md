---
name: blogone
title: Ted Tschopp's Blog
author: Ted Tschopp
layout: default
permalink: /2015/01/29/mobile-computing/
image: img/blog.jpg
lead: A collection of writings I have put online over the years. Some of it is really bad, and some of it I am proud of. All of it can be made better.
---
  <ul>
  {% for post in site.posts limit:5 %}
    <li>
      {% assign d = post.date | date: "%-d" %}{% assign m = post.date | date: "%B" %}{% assign dy = post.date | date: "%A" %}
      <a href="{{ post.url }}">{{ post.title }} <!-- -- {{ dy }}, {{ m }} {% case d %}{% when '1' or '21' or '31' %}{{ d }}st{% when '2' or '22' %}{{ d }}nd{% when '3' or '23' %}{{ d }}rd{% else %}{{ d }}th{% endcase %}, {{ post.date | date: "%Y" }}
      </a>
      {% if forloop.first %}
      <p>{{ post.content |truncatehtml | truncatewords: 20 }}</p>
      {% endif %} -->
    </li>
  {% endfor %}
  </ul>
