---
title: Schedule (subject to change as the term progresses)
---

<style>
.sched-row {
  display: grid;
  grid-template-columns: 4.5rem 10rem 1fr;
  grid-template-areas: "date topic papers";
  border-top: 1px solid #eeebee;
}
.sched-row:first-child { border-top: none; }
.sched-row > div { padding: 0.5rem 0.75rem; min-width: 0; }
.sched-date {
  grid-area: date;
  text-align: right;
  white-space: nowrap;
  color: #5c5962;
}
.sched-date::after { content: ":"; }
.sched-topic { grid-area: topic; font-weight: 600; }
.sched-papers { grid-area: papers; }
.sched-papers > .paper {
  display: flex;
  align-items: baseline;
  gap: 1rem;
}
.sched-papers > .paper > a {        /* paper title -> slides (single line, ellipsis) */
  flex: 1 1 auto;
  min-width: 0;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.sched-papers > .paper + .paper {
  border-top: 1px solid #e7e7e7;     /* light grey line between the two papers */
  margin-top: 0.4rem;
  padding-top: 0.4rem;
}
.sched-papers .paper-link {          /* the "paper" link -> never shrinks/wraps */
  flex: 0 0 auto;
  white-space: nowrap;
}
@media (max-width: 44rem) {
  .sched-row {
    grid-template-columns: 3.5rem 1fr;
    grid-template-areas:
      "date topic"
      "date papers";
  }
  .sched-row > div { padding: 0.4rem 0.5rem; }
  .sched-topic { padding-bottom: 0; }
  .sched-papers { padding-top: 0.15rem; }
}
</style>

<div class="sched">
  <div class="sched-row">
    <div class="sched-date">Jan 12</div>
    <div class="sched-topic">Overview</div>
    <div class="sched-papers">
      <div class="paper"><a href="https://docs.google.com/presentation/d/1EGUaR_Q_unPv50d6CB_W-_kQ-QbcV2k59bG0avkUUPw/edit?usp=sharing">Course Overview</a><span class="paper-link"><a href="https://www.cs.jhu.edu/~jason/advice/how-to-read-a-paper.html">How to read a paper</a></span></div>
    </div>
  </div>
{%- for day in site.data.schedule %}
  <div class="sched-row">
    <div class="sched-date">{{ day.date }}</div>
    <div class="sched-topic">{{ day.topic }}</div>
    <div class="sched-papers">
    {%- for p in day.papers %}
      <div class="paper"><a href="{{ p.slides | relative_url }}" title="{{ p.title | escape }}">{{ p.title | truncate: 60, "…" }}</a>{% if p.arxiv %}<span class="paper-link"><a href="{{ p.arxiv }}">paper</a></span>{% endif %}</div>
    {%- endfor %}
    </div>
  </div>
{%- endfor %}
</div>
