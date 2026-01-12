---
layout: page
title: Calendar
description: Listing of course modules and topics.
---

A tentative plan for the schedule (topics, deadlines, etc.) is available [here](https://gtvault-my.sharepoint.com/:x:/g/personal/wxu358_gatech_edu/IQBnkSig8PpFR5si8nvJ5LEmAeds9hwiaErqfdz9DOs6TQg?e=UA6PCe).


{% for module in site.modules %}
{{ module }}
{% endfor %}
