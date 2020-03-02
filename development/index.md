---
layout: simple
title: Development Blog
---
{% assign blog_posts = site.pages | where: "layout", "blog" | sort: "date" | reverse %}
{% for post in blog_posts %}
	{% unless post.draft %}
		{% include post-summary.html post=post index=forloop.index %}
	{% endunless %}
{% endfor %}