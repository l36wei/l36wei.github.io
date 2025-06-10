---
layout: page
title: Teaching
permalink: /teaching/
nav: true
nav_order: 4
---

<style>
.teaching-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}
.teaching-card {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  padding: 1.5rem;
  text-align: center;
  transition: transform 0.2s;
  cursor: pointer;
}
.teaching-card:hover {
  transform: scale(1.07);
  box-shadow: 0 4px 16px rgba(0,0,0,0.16);
  z-index: 2;
}
.teaching-icon {
  width: 40px;
  height: 40px;
  margin-bottom: 0.5rem;
}
.teaching-title {
  font-size: 1.1rem;
  font-weight: bold;
  margin: 0.5rem 0 0.2rem 0;
}
.teaching-index {
  color: #888;
  font-size: 0.95rem;
  margin-bottom: 0.3rem;
}
</style>

<div class="teaching-grid">
  {% assign sorted_courses = site.teaching | sort: "index" %}
  {% for course in sorted_courses %}
    <div class="teaching-card" onclick="location.href='{{ course.course_url | default: course.url }}'">
      <img class="teaching-icon" src="{{ '/assets/icons/' | append: course.icon }}" alt="icon"/>
      <div class="teaching-index">#{{ course.index }}</div>
      <div class="teaching-title">
        <a href="{{ course.course_url | default: course.url }}">{{ course.title }}</a>
      </div>
    </div>
  {% endfor %}
</div>
