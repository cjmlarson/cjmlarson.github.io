---
layout: page
title: "Updates"
permalink: /updates/
description:
nav: true
nav_order: 2
---

<div style="margin-bottom: 2rem;"></div>

<!-- Blog posts -->
<div class="posts">
  {% assign sorted_posts = site.posts | sort: 'date' | reverse %}
  
  {% for post in sorted_posts %}
    <article class="post-preview">
      <h3>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      
      <p class="post-meta">
        {{ post.date | date: "%B %d, %Y" }}
        {% if post.categories %}
          &nbsp;&middot;&nbsp;
          {% for category in post.categories %}
            <span class="category">{{ category }}</span>
            {% unless forloop.last %}, {% endunless %}
          {% endfor %}
        {% endif %}
      </p>
      
      {% if post.description %}
        <p class="post-description">{{ post.description }}</p>
      {% endif %}
      
      {% if post.tags %}
        <p class="post-tags">
          {% for tag in post.tags %}
            <span class="tag">#{{ tag }}</span>
            {% unless forloop.last %}&nbsp;{% endunless %}
          {% endfor %}
        </p>
      {% endif %}
      
      <hr>
    </article>
  {% endfor %}
  
  {% if sorted_posts.size == 0 %}
    <p>No posts yet. Check back soon!</p>
  {% endif %}
</div>

<style>
.post-preview {
  margin-bottom: 2rem;
}

.post-preview h3 {
  margin-bottom: 0.5rem;
}

.post-preview h3 a {
  color: var(--global-text-color);
  text-decoration: none;
}

.post-preview h3 a:hover {
  color: var(--global-theme-color);
}

.post-meta {
  color: var(--global-text-color-light);
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.post-description {
  margin-bottom: 0.5rem;
}

.post-tags {
  margin-bottom: 0.5rem;
}

.tag {
  background-color: var(--global-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 3px;
  padding: 0.2rem 0.5rem;
  font-size: 0.85rem;
  color: var(--global-text-color-light);
}

.category {
  font-weight: 500;
  color: var(--global-theme-color);
}

.post-preview hr {
  margin-top: 1.5rem;
  border: none;
  border-top: 1px solid var(--global-divider-color);
}
</style>