---
title: "Small Games"
permalink: /games/
layout: single
author_profile: true
---

This is a collection of small games and tools.

{% for game in site.games %}
- [{{ game.title }}]({{ game.permalink }})
{% endfor %}
