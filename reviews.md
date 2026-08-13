---
layout: page
title: Tool Reviews
permalink: /reviews/
---

<!-- Same pattern again, this time over the `_reviews` collection. -->
<ul class="post-list">
{% for review in site.reviews %}
  <li>
    <a href="{{ review.url | relative_url }}">{{ review.title }}</a>
    {% if review.verdict %}<span class="meta">{{ review.verdict }}</span>{% endif %}
  </li>
{% endfor %}
</ul>

{% if site.reviews.size == 0 %}
  <p class="muted">Nothing here yet — check back soon.</p>
{% endif %}
