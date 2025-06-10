---
layout: page
title: teaching
permalink: /teaching/
nav: true
nav_order: 6
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
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.2s, box-shadow 0.2s;
  display: flex;
  flex-direction: column;
  height: 100%;
}
.teaching-card:hover {
  transform: scale(1.07);
  box-shadow: 0 4px 16px rgba(0,0,0,0.16);
  z-index: 2;
}
.teaching-card-img {
  width: 100%;
  height: 140px;
  object-fit: cover;
  background: #f5f5f5;
}
.teaching-card-body {
  padding: 1rem;
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.teaching-title {
  font-size: 1.1rem;
  font-weight: bold;
  margin: 0.5rem 0 0.2rem 0;
  text-align: center;
}
.teaching-desc {
  color: #555;
  font-size: 0.98rem;
  text-align: center;
}
</style>

<div class="teaching-grid">
  {% assign sorted_courses = site.teaching | sort: "index" %}
  {% for course in sorted_courses %}
    <div class="teaching-card" onclick="window.open('{{ course.course_url }}', '_blank')">
      <img class="teaching-card-img" src="{{ '/assets/course-images/' | append: course.image }}" alt="{{ course.title }}">
      <div class="teaching-card-body">
        <div class="teaching-title">{{ course.title }}</div>
        <div class="teaching-desc">{{ course.description }}</div>
      </div>
    </div>
  {% endfor %}
</div>
