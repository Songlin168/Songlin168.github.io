---
layout: page
title: Activities
permalink: /activities/
description: Research visits, presentations, posters, demonstrations, and professional events.
nav: true
nav_order: 3
---

<style>
  .post-header {
    display: none;
  }
</style>

<div class="activities">
  <section class="mb-5">
    <h2 class="mb-4">Research Visits</h2>
    <div class="row row-cols-1 row-cols-md-2 g-4">
      {% for visit in site.data.activities.research_visits %}
        <div class="col mb-4">
          <article class="card h-100 shadow-sm border-0">
            {% if visit.image %}
              <img src="{{ visit.image | relative_url }}" class="card-img-top" alt="{{ visit.alt }}" loading="lazy">
            {% else %}
              <div class="bg-light text-center py-5" aria-label="Photo to be added">
                <i class="fa-solid fa-building-columns fa-3x text-muted" aria-hidden="true"></i>
              </div>
            {% endif %}
            <div class="card-body">
              <div class="d-flex justify-content-between align-items-start gap-3 mb-2">
                <span class="badge rounded-pill text-bg-primary">Research Visit</span>
                <span class="text-muted small">{{ visit.year }}</span>
              </div>
              <h3 class="h5 card-title">{{ visit.institution }}</h3>
              <p class="card-text text-muted mb-0">
                <i class="fa-solid fa-calendar-days me-1" aria-hidden="true"></i> {{ visit.date }}<br>
                <i class="fa-solid fa-location-dot me-1" aria-hidden="true"></i> {{ visit.location }}
              </p>
            </div>
          </article>
        </div>
      {% endfor %}
    </div>
  </section>

  <section>
    <h2 class="mb-4">Presentations</h2>
    <div class="row row-cols-1 row-cols-md-2 g-4">
      {% for activity in site.data.activities.presentations %}
        <div class="col mb-4">
          <article class="card h-100 shadow-sm border-0">
            <div class="card-body d-flex flex-column">
              <div class="d-flex justify-content-between align-items-start gap-3 mb-2">
                <span class="badge rounded-pill text-bg-primary">{{ activity.type }}</span>
                <span class="text-muted small">{{ activity.year }}</span>
              </div>
              <h3 class="h5 card-title">{{ activity.title }}</h3>
              <p class="card-text text-muted mb-3">
                <i class="fa-solid fa-calendar-days me-1" aria-hidden="true"></i> {{ activity.date }}<br>
                <i class="fa-solid fa-location-dot me-1" aria-hidden="true"></i> {{ activity.location }}
              </p>
              {% if activity.pdf %}
                <div class="mt-auto">
                  <a class="btn btn-sm btn-outline-primary" href="{{ activity.pdf | relative_url }}" target="_blank" rel="noopener noreferrer">
                    <i class="fa-solid fa-file-pdf me-1" aria-hidden="true"></i> View PDF
                  </a>
                </div>
              {% endif %}
            </div>
          </article>
        </div>
      {% endfor %}
    </div>
  </section>
</div>
