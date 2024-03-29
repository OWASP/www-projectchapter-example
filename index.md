---

layout: col-sidebar
title: OWASP Project-Chapter Example
tags: example-tag
level: 2
type: example
altfooter: true
meetup-group: OWASP-Austin-Chapter
country: 
postal-code: 

---

<link rel="stylesheet" href="{{site.base_url}}/assets/css/styles.css">
<!-- rebuild 35 -->
{% include address_multiline.html %}

{% assign i18n = site.data.i18n_en | where: 'id', 'index' | first %}

{{ i18n.intro | markdownify }}

**Quick test - something something - Something else**

### A List of Donors

{% assign individual_supporter = site.data.ow_attributions | uniq %}
{% for supporter in individual_supporter %}
* {{ supporter | strip_html | strip_newlines | strip }}
{% endfor %}

| Heading 1 | Heading 2 | Heading 3 |
| --- | --- | --- |
| Data | More Data | Even More Data |
| Hello | New | World |


<section id="jumphere">
  This is a test of the jump here fragment
  </section>

:+1:


{% for m in site.data.tstmenu %}
MENU
{% endfor %}

<section class="homepage-blog">
  <h2><a href="{{ site.posts.first.url }}">{{ site.posts.first.title }}</a></h2>
<a><img src="{{ site.posts.first.author_image }}" alt="image"></a>
<p class="author"><a>{{ site.posts.first.author }}</a><span style="color:#7C7C7C">, {{ site.posts.first.date | date: "%B %e, %Y" }}</span></p>
<p>{{ site.posts.first.excerpt }}<a href="/www-projectchapter-example{{ site.posts.first.url }}">...read more</a></p>
</section>

<a class='timeclass'>12:00 - 13:00 - Opening Session</a>

#### Testing theme data elements
{% for project in site.data.projects %}
{{ project.name }}
{% endfor %}

{% assign category = site.data.events | where: "category", "Global" | first %}
   <ul>
      {% for event in category.events %}
      <li><a href="{{event.url}}" target="_blank" rel="noopener">{{event.name}}</a></li>
      {% endfor %}
   </ul>
   
### Check our Upcoming Meetup Events:
{% include chapter_events.html group=page.meetup-group %}


<script type='text/javascript'>
  $(function(){
    $(".timeclass").hover(function() {
      utc_str = $(this).text();
      ndx = utc_str.indexOf(':');
      st_hour_str = utc_str.substring(0, ndx);
      st_min_str = utc_str.substring(ndx + 1, ndx + 3);
      utc_dt = luxon.DateTime.utc(2020, 06, 06, parseInt(st_hour_str), parseInt(st_min_str), 0);
      start_dt = utc_dt.setZone(luxon.DateTime.local().zoneName);

      ndx = utc_str.lastIndexOf(':');
      end_hour_str = utc_str.substring(ndx - 2, ndx - 1);
      end_min_str = utc_str.substring(ndx + 1, ndx + 3);
      utc_dt = luxon.DateTime.utc(2020, 06, 06, parseInt(end_hour_str), parseInt(end_min_str), 0);
      end_dt = utc_dt.setZone(luxon.DateTime.local().zoneName);
      popstr = start_dt.toLocaleString(luxon.DateTime.TIME_WITH_SECONDS) + ' to ' + end_dt.toLocaleString(luxon.DateTime.TIME_WITH_SHORT_OFFSET);
      $(this).prop('title', popstr);
    });
  });  
</script>

