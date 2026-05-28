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
    <th scope="row" style="width: 15%; white-space: nowrap">
      <span style="background-color: #fce4ec; color: #c2185b; font-size: 0.72rem; font-weight: 600; padding: 2px 7px; border-radius: 4px; letter-spacing: 0.03em;">{{ item.date | date: '%b %Y' }}</span>
    </th>
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
