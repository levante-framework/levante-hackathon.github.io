---
layout: default
title: Speakers
permalink: /speakers/
---

### Speakers
Listed alphabetically by first name. Most speakers are LEVANTE team members at Stanford or from affiliated partner sites. 

<div class="speakers-grid">
  {% for s in site.speakers %}
    <article class="speaker-card">
      <!-- Image (optional: linking the image to website too) -->
      {% if s.website %}
        <a href="{{ s.website }}" target="_blank" rel="noopener noreferrer">
          <img src="{{ s.photo | relative_url }}" alt="Photo of {{ s.name }}" class="speaker-photo" />
        </a>
      {% else %}
        <img src="{{ s.photo | relative_url }}" alt="Photo of {{ s.name }}" class="speaker-photo" />
      {% endif %}

      <!-- Name linking to external site (opens in new tab) -->
      <h2 class="speaker-name">
        {% if s.website %}
          <a href="{{ s.website }}" target="_blank" rel="noopener noreferrer">{{ s.name }}</a>
        {% else %}
          {{ s.name }}
        {% endif %}
      </h2>

      <p class="speaker-title">{{ s.title }}</p>
      <p class="speaker-institution">{{ s.institution }}</p>
    </article>
  {% endfor %}
</div>

<style>
/* simple styles you can paste into your main CSS instead */
.speakers-grid{
  display:grid;
  grid-template-columns: repeat(auto-fit,minmax(200px,1fr));
  gap:1rem;
  margin-top:1rem;
}
.speaker-card{
  text-align:center;
  padding:0.75rem;
  border:1px solid #eee;
  border-radius:8px;
  background: #fff;
}
.speaker-photo{
  width:120px;
  height:120px;
  object-fit:cover;
  border-radius:50%;
  display:block;
  margin:0 auto 0.5rem;
}
.speaker-name{ font-size:1.05rem; margin:0.2rem 0; }
.speaker-title, .speaker-institution{ margin:0; font-size:0.9rem; color:#555; }
</style>
