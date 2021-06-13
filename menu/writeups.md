---
layout: page
title: Posts
---
<ul class="posts">
  {% for writeup in site.categories.writeups %}

    {% unless writeup.next %}
      <h3>{{ writeup.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ writeup.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ writeup.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ writeup.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li itemscope>
      <a href="{{ site.github.url }}{{ writeup.url }}">{{ writeup.title }}</a>
      <p class="writeup-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ writeup.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>
    </li>

  {% endfor %}
</ul>
