---
layout: page
title: Writing
permalink: /writing/
---

<!-- `site.posts` is every file in _posts/, newest first, automatically —
     Jekyll builds this list for you, you don't maintain it by hand. This
     covers everything: articles, notes, and tool reviews alike, all in
     one place. -->
<ul class="post-list">
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="meta">{{ post.date | date: "%B %-d, %Y" }}</span>
  </li>
{% endfor %}
</ul>

{% if site.posts.size == 0 %}
  <p class="muted">No writing yet — check back soon.</p>
{% endif %}
