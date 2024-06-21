---
layout: people
title: People
subtitle: #Lab members, collaborators and associates
banner_image: null
permalink: /people/
---

<!-- Content here would show up above the people on your team -->

{% for person in site.data.people %}
<div class="person-profile">
  <p><strong>{{ person.name }}</strong></p>
  <p>{{ person.role }}</p>
  <a href="/people/{{ person.id }}.md" target="_blank">
    {{ person.icon | markdownify | remove: "<p>" | remove: "</p>" }} View Description
  </a>
</div>
{% endfor %}