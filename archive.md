---
layout: page
title: Archive
permalink: /archive
---

# Archive

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
        <span class="small">{{ post.date | date: '%B %d, %Y' }}</span>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
