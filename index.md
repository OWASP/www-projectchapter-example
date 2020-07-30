---

layout: col-sidebar
title: OWASP [GROUPNAME]
tags: example-tag
level: 4
type: example
altfooter: true

---


<!-- rebuild 14 -->
This is an example of a Project or Chapter Page.  Please change these items to indicate the actual information you wish to present.  In addition to this information, the 'front-matter' above this text should be modified to reflect your actual information.  An explanation of each of the front-matter items is below:

layout: This is the layout used by project and chapter pages.  You should leave this value as col-sidebar

title: This is the title of your project or chapter page, usually the name.  For example, OWASP Zed Attack Proxy or OWASP Baltimore

tags: This is a space-delimited list of tags you associate with your project or chapter.  If you are using tabs, at least one of these tags should be unique in order to be used in the tabs files (an example tab is included in this repo) 

level: For projects, this is your project level (2 - Incubator, 3 - Lab, 4 - Flagship)

type: For projects, one of documentation, code, or tool

A good resource for github markdown tags can be found [here]([https://www2.owasp.org/migration)

### List of Donors

{% assign individual_supporter = site.data.ow_attributions | uniq %}
{% for supporter in individual_supporter %}
* {{ supporter | strip_html | strip_newlines | strip }}
{% endfor %}



<section id="jumphere">
  This is a test of the jump here fragment
  </section>

:+1:

<a class='timeclass'>12:00 - 13:00 - Opening Session</a>

### Check our Upcoming Meetup Events:
{% include chapter_events.html group='owasp-los-angeles' %}

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
