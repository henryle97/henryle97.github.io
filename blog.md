---
layout: page
permalink: /blog/
title: Blog
subtitle: >-
  Notes from production — inference, document AI, and the parts of a system
  that only show up once a model meets real hardware.
---

<section class="section">
  <div class="wrap">
    {% if site.posts.size > 0 %}
    <ul class="post-list">
      {%- for post in site.posts %}
      <li class="post-item">
        <a class="post-item-link" href="{{ post.url | relative_url }}">
          <time class="post-item-date" datetime="{{ post.date | date_to_xmlschema }}">
            {{ post.date | date: '%B %-d, %Y' }}
          </time>
          <h2 class="post-item-title">{{ post.title }}</h2>
          {%- if post.subtitle %}
          <p class="post-item-summary">{{ post.subtitle }}</p>
          {%- endif %}
        </a>
        {%- if post.tags and post.tags.size > 0 %}
        <ul class="tags">
          {%- for tag in post.tags %}
          <li class="tag">{{ tag }}</li>
          {%- endfor %}
        </ul>
        {%- endif %}
      </li>
      {%- endfor %}
    </ul>
    {% else %}
    <p class="post-empty">Nothing published yet. Check back soon.</p>
    {% endif %}
  </div>
</section>
