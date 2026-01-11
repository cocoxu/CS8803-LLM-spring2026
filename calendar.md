---
layout: page
title: Calendar
description: Listing of course modules and topics.
---

A tentative plan for the schedule (topics, deadlines, etc.) is available [here](https://docs.google.com/spreadsheets/d/1TNRX8EZKsFB5OO-GA1HYtacDTr6L1aT0mLbG1V6hSwA/edit?usp=sharing).


{% for module in site.modules %}
{{ module }}
{% endfor %}
