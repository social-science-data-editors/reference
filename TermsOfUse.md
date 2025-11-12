---
title: Various terms of use
layout: withtable
---
Each entry in the database will list a data provider, an extract from the terms of use, and the source URL for the terms of use. There is an indication on whether extracts from the data provider can be redistributed by academics as part of replication packages (an important caveat!), and whether data from the data provider can be shared privately (not for publication) with data editors and other members of the journal's editorial time for "audit" purposes. When available, there may be separate page with further details.

> Search the database for any keyword in any field.


<table class="display">
  {% for row in site.data.termsofuse %}
    {% if forloop.first %}
    <thead>
    <tr>
      <th> Data provider" </th>
      <th> Terms of Use" </th>
      <th>Source URL</th>
      <th>  Distributable </th>
      <th> Shareable with journal? </th>
      <th> Further info</th>
      <th> Contributed by</th>
    </tr>
    </thead>
    {% endif %}
  <!-- Only display rows that are have an empty "obsolete" field -->
  <!-- manually constructing table -->
  <!-- Data provider,Terms of Use,Source URL,Distributable,Further info,Contributed,Lastdate -->
  {% if row["Obsolete"] %}
    <!-- Data for {{ row["Data provider"] }} ({{ row["Lastdate"] }}) was obsoleted on {{ row["Obsolete"] }} -->
  {% else %}
  <tr>
    <td> {{ row["Data provider"] }} </td>
    <td> {{ row["Terms of Use"] }} </td>
    <td> <a href="{{ row["Source URL"] }}" alt="Link to Terms of Use">{{ row["Source URL"] }}</a></td>
    <td> {{ row["Distributable"] }} </td>
    <td> {{ row["Shareable with Journal"] }} </td>
    {% if row["Further info"] %}
    <td> <a href="information/{{ row["Further info"] }}.html" alt="Link to additional information">Yes</a></td>
    {% else %}
    <td></td>
    {% endif %}
    <td class="contributor">{{ row["Contributed"] }}<br/>{{ row["Lastdate"] }}</td>
  </tr>
  {% endif %}
  {% endfor %}
</table>



To download the entire database in CSV format, [click here](https://raw.githubusercontent.com/social-science-data-editors/reference/main/_data/termsofuse.csv).