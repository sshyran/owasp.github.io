---

title: Upcoming OWASP Chapter Meetup Events (next 30 days)
layout: col-sidebar
permalink: /chapters/events/

---

<br>
{% assign events = site.data.chapter_events | sort: 'date' %}
{% assign prevdate = nil %}
{% for event in events %}
{% assign evdate = event.date | date: "%B %d, %Y" %}
{% if evdate <> prevdate %}
---
## {{ evdate }}
---
{% assign prevdate = evdate %}
{% endif %}
### Event: {{ event.name }}
#### Chapter: [{{ event.chapter }}](/{{ event.repo }}/)
#### Time: {{ event.time }} ({{ event.timezone }})
#### Link: [{{ event.link }}]({{ event.link }})
<div>
<strong>Description</strong>: {{ event.description }}
</div>
<br>
{% endfor %}