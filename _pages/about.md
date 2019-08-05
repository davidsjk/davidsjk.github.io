---
title: "About"
permalink: /about/
header:
  image: "/images/los_skyline.jpg"
---

I am a student of data science who is learning and gaining practical experience
at a rapid pace.

{% include base_path %}
{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
