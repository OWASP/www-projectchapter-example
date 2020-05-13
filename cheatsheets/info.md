{% assign cheatsheets = site.pages | where_exp: "page", "page.tags contains page.document" %}
<ul>
{% for pg in cheatsheets %}
<li><a href="{{site.github.url}}{{pg.url}}">
<span style='font-size:{% if page.title contains pg.title %}normal{%else%}smaller{%endif%};text-decoration:none;{% if page.title contains pg.title %}font-weight: bold;{% endif %}'>{{ pg.title | remove: 'Cheat Sheet' | remove: 'Cheatsheet' }}
</span></a></li>
{% endfor %}
</ul>