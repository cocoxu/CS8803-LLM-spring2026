---
title: Schedule (subject to change as the term progresses)
---

<dl>
  <dt>Jan 12</dt>
  <dd>
    <dl>
      <dt><a href="https://docs.google.com/presentation/d/1EGUaR_Q_unPv50d6CB_W-_kQ-QbcV2k59bG0avkUUPw/edit?usp=sharing">Course Overview</a></dt>
      <dd><a href="https://www.cs.jhu.edu/~jason/advice/how-to-read-a-paper.html">How to read a paper</a></dd>
    </dl>
  </dd>
{%- for day in site.data.schedule %}
  <dt>{{ day.date }}</dt>
  <dd>
  {%- for p in day.papers %}
    <dl>
      <dt><a href="{{ p.slides | relative_url }}" title="{{ p.title | escape }}">{{ p.title | truncate: 62, "…" }}</a></dt>
      <dd>{% if p.arxiv %}<a href="{{ p.arxiv }}">{{ p.arxiv_label | default: "arXiv" }}</a>{% endif %}</dd>
    </dl>
  {%- endfor %}
  </dd>
{%- endfor %}
</dl>
