---
layout: default
---

{% for post in site.posts %}

<ul>
 
<li>
	<h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}</h4>
</li>
 
</ul>
{% endfor %}

