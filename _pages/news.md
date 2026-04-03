---
layout: page
title: news
permalink: /news/
nav: true
nav_order: 2
---

{% assign all_news = site.news | reverse %}
<table class="table table-sm table-borderless">
{% for item in all_news %}
  <tr>
    <th scope="row" style="width: 15%; white-space: nowrap">{{ item.date | date: '%b %Y' }}</th>
    <td>
      {% if item.inline %}
        {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
      {% else %}
        <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      {% endif %}
    </td>
  </tr>
{% endfor %}
</table>
