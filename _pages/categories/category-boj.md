---
title: "잡담"
layout: archive
permalink: categories/boj
author_profile: true
sidebar:
    nav: "docs"
---


***

{% assign posts = site.categories.notepad %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}