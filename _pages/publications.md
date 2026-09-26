---
title: "Publications"
permalink: /publications/
author_profile: true
---

{% assign publications = site.publications | sort: 'date' | reverse %}
My publication record spans intelligent networking, critical infrastructure protection, AI-enabled observability, zero trust security, and post-quantum resilience.

{% for post in publications %}
{{ post.citation }}

{% if post.paperurl %}[Access publication]({{ post.paperurl }}){% else %}[Access publication](https://scholar.google.com/citations?hl=en&authuser=1&user=XADxRNkAAAAJ){% endif %}

{% endfor %}
