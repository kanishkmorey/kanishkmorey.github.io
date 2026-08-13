---
layout: page
title: Projects
permalink: /projects/
---

<!-- `site.projects` is every file in _projects/ — the collection defined
     in _config.yml. Same idea as site.posts above, just a different
     collection name. -->
<ul class="post-list">
{% for project in site.projects %}
  <li>
    <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    {% if project.summary %}<span class="meta">{{ project.summary }}</span>{% endif %}
  </li>
{% endfor %}
</ul>

{% if site.projects.size == 0 %}
  <p class="muted">Nothing here yet — check back soon.</p>
{% endif %}
