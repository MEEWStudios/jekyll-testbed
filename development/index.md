---
layout: simple
title: Development Blog
---
{% assign blog_posts = site.pages | where: "layout", "blog" | sort: "date" | reverse %}
{% for post in blog_posts %}
	{% unless post.draft %}
	<div class='container title'>
		<div>
			<h2>{{forloop.index}}</h2>
			<h2>{{post.title}}</h2>
		</div>
		{{post.content | truncatewords: 40}}
		<div>
			<a class='button' href='{{page.url}}'>Read</a>
		</div>
	</div>
	{% endunless %}
{% endfor %}