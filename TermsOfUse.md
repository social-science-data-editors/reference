---
title: Various terms of use
layout: withtable
---
Each entry in the database will list a data provider, an extract from the terms of use, and the source URL for the terms of use. There is an indication on whether extracts from the data provider can be redistributed by academics as part of replication packages (an important caveat!). When available, there may be separate page with further details.

> Search the database for any keyword in any field.


<table class="display">
  {% for row in site.data.termsofuse %}
    {% if forloop.first %}
    <thead>
    <tr>
      {% for cell in row %}
        <th>{{ cell[0] }}</th>
      {% endfor %}
    </tr>
    </thead>
    {% endif %}
{% comment %}
    {% tablerow cell in row %}
      {{ cell[1] }}
    {% endtablerow %}
{% endcomment %}
  {% endfor %}
</table>



To download the entire database, [click here](https://raw.githubusercontent.com/social-science-data-editors/reference/main/_data/termsofuse.csv).