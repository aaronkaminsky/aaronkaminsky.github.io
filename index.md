---
layout: default
title: Home
---

<div class="glass-card">
  <blockquote class="quote">
    "The universe is full of magical things, patiently waiting for our wits to grow sharper."
    <cite class="quote-author">&mdash; Eden Phillpotts</cite>
  </blockquote>
  <p class="intro">
    Welcome to my personal sandbox. Feel free to explore the links below, or just enjoy the stillness.
  </p>

  <div class="card-section">
    <span class="section-label">Projects</span>
    <div class="minimal-links">
      {% for project in site.data.projects %}
      <a href="{{ project.url }}" class="btn primary" target="_blank" rel="noopener noreferrer">{{ project.name }}</a>
      {% endfor %}
    </div>
  </div>

  <div class="card-separator"></div>

  <div class="card-section">
    <span class="section-label">Connect</span>
    <div class="minimal-links">
      {% for link in site.data.links %}
      <a href="{{ link.url }}" class="btn secondary" target="_blank" rel="noopener noreferrer">{{ link.title }}</a>
      {% endfor %}
    </div>
  </div>
</div>
