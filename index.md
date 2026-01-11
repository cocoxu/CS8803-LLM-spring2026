---
layout: home
title: CS 8803 - LLM
nav_exclude: true
seo:
  type: Course
  name: Just the Class
---

# {{ site.tagline }}
{: .mb-2 }
{{ site.description }}
{: .fs-6 .fw-300 }

{% if site.announcements %}
{{ site.announcements.last }}
[Announcements](announcements.md){: .btn .btn-outline .fs-3 }
{% endif %}


- Instructor: [Wei Xu](https://cocoxu.github.io) 
- Lecture: Mondays, Wednesdays 2:00-3:15pm
{% for module in site.modules %}
{{ module }}
{% endfor %}
