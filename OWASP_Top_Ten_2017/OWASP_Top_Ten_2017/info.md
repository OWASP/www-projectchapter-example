### Table of Contents
{% assign base_url = '/www-projectchapter-example' %}
{% assign devsite = site.static_files | where: 'name', 'devsite.txt' %}
{% if devsite.size > 0 %}
{% assign base_url = '' %}
{% endif %}
{% assign top_ten_pages = site.pages | where:"document","OWASP Top Ten 2017" | sort: "order" %}
<ul>
{% for ttp in top_ten_pages %}
{% unless ttp.order == 0 %}
<li><a href="{{ base_url }}{{ ttp.url }}">{{ ttp.title }}</a></li>
{% endunless %}
{% endfor %}
</ul>