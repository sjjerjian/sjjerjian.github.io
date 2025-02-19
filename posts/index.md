---
layout: default
title: Posts
---

{% if page.toc %}
  {% include toc-sidebar.html %}
{% endif %}

<div class="posts-list">
  {% for post in site.posts %}
  <article class="post-preview">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <div class="post-meta">
      {{ post.date | date: "%B %d, %Y" }}
    </div>

    <div class="post-entry">
      {% if post.thumbnail %}
      <div class="post-image">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.thumbnail | relative_url }}" alt="Post thumbnail">
        </a>
      </div>
      {% endif %}
      
      <div class="post-excerpt">
        {% if post.excerpt %}
          {{ post.excerpt | strip_html | truncatewords: 50 }}
        {% endif %}
        <a href="{{ post.url | relative_url }}" class="read-more">Read More »</a>
      </div>
    </div>

    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags: 
      {% for tag in post.tags %}
      <span>{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </article>
  {% endfor %}
</div>