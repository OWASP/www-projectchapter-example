{% assign cheatsheets = site.pages | where_exp: "page", "page.tags contains page.document" %}
<ul>
{% for page in cheatsheets %}
<li><a href="{{site.github.url}}{{page.url}}"><span style='font-size:smaller;text-decoration:none;'>{{ page.title | remove: 'Cheat Sheet' | remove: 'Cheatsheet' }}</span></a></li>
{% endfor %}
</ul>