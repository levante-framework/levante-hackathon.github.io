---
layout: default
title: Speakers
permalink: /speakers/
---

<link rel="stylesheet" href="{{ '/assets/css/speakers.css' | relative_url }}">

<section class="speakers-page">
  <header class="speakers-header">
    <h1>{{ page.title }}</h1>
    <p class="speakers-sub">Short intro sentence or tagline goes here.</p>
  </header>

  <div class="speakers-grid" role="list">
    {% for speaker in site.data.speakers %}
      <article class="speaker-card" role="listitem">
        <div class="speaker-photo-wrap">
          <img class="speaker-photo" src="{{ speaker.img | relative_url }}" alt="{{ speaker.alt | default: speaker.name }}" loading="lazy" width="320" height="320">
        </div>

        <div class="speaker-body">
          <h3 class="speaker-name">
            {% if speaker.webpage %}
              <a href="{{ speaker.webpage }}" target="_blank" rel="noopener">{{ speaker.name }}</a>
            {% else %}
              {{ speaker.name }}
            {% endif %}
          </h3>

          {% if speaker.title %}
            <div class="speaker-title">{{ speaker.title }}</div>
          {% endif %}

          {% if speaker.affil %}
            <div class="speaker-affil">{{ speaker.affil }}</div>
          {% endif %}
        </div>
      </article>
    {% endfor %}
  </div>
</section>
