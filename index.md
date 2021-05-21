---

layout: col-sidebar
title: OWASP Project-Chapter Example
tags: example-tag
level: 4
type: example
altfooter: true
meetup-group: owasp-los-angeles
country: 
postal-code: 

---

<link rel="stylesheet" href="/www-projectchapter-example/assets/css/styles.css">
<!-- rebuild 24 -->


{% assign i18n = site.data.i18n_en | where: 'id', 'index' | first %}

{{ i18n.intro | markdownify }}



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


{% for m in site.data.tstmenu.yml %}
MENU
{% endfor %}


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
