---
layout: page
title: Blog
permalink: /blog/
---

<!-- `site.posts` is every file in _posts/, newest first, automatically —
     Jekyll builds this list for you, you don't maintain it by hand. -->
<ul class="post-list">
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="meta">{{ post.date | date: "%B %-d, %Y" }}</span>
  </li>
{% endfor %}
</ul>

{% if site.posts.size == 0 %}
  <p class="muted">No posts yet — check back soon.</p>
{% endif %}
