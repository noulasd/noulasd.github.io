---
layout: archive
title: "Misc"
permalink: /misc/
author_profile: true
---

That hidden coauthor:
<img src="{{ site.baseurl }}/images/coauthor.jpg" alt="coauthor" height="300" width="250">


{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.misc reversed %}
  {% include archive-single-talk.html %}
{% endfor %}



