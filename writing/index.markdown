---
layout: default
title: Writing
---

<ul>
  {% assign posts = site.writing | sort: "date" | reverse %}
  {% for post in posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {% if post.date %}
        <span class="meta">
          — {{ post.date | date: "%Y-%m-%d" }}
        </span>
      {% endif %}
    </li>
  {% endfor %}
</ul>
