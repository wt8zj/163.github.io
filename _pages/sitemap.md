---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

<!--
<h2>Main Pages</h2>
- [Home]({{ "/" | relative_url }})
- [About]({{ "/about/" | relative_url }})
- [Contact]({{ "/contact/" | relative_url }})
- [CV]({{ "/cv/" | relative_url }})

<h2>Publications</h2>
{% for publication in site.publications %}
  {% include archive-single.html %}
{% endfor %}

<h2>Teaching</h2>
{% for teaching in site.teaching %}
  {% include archive-single.html %}
{% endfor %}
-->
<!--
A list of all the posts and pages found on the site. For you robots out there is an [XML version]({{ base_path }}/sitemap.xml) available for digesting as well.
-->
<h2>Pages</h2>
{% for post in site.pages %}
  {% include archive-single.html %}
{% endfor %}

<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}
