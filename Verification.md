---
title: Verification when data are not publishable
layout: withtable
---

Researcher in economics often use databases that are sensitive, proprietary, or otherwise not publishable while respecting legal, contractual, and ethical constraints. 

In more recent years, data editors and institutions have been working to nevertheless allow for ways to verify the computational reproducibility of research using such data. This involves a variety of actors: sending replicators to such institutions, requesting a credible third-party report, etc. No single solutions works uniformly. 

The below database reports on successful verifications known to data editors, and their constraints. See [definitions](#definitions) for key terms. 

> Search the database for any keyword in any field.


<table class="display">
  {% for row in site.data.verifications %}
    {% if forloop.first %}
    <thead>
    <tr>
      <th> Institution </th>
      <th> Verification type </th>
      <th> Research approval</th>
      <th> Initiator </th>
      <th> Verifier (if different) </th>
      <th> Further info</th>
      <th> Notes </th>
      <th> Examples </th>
      <th> Contributed by</th>
    </tr>
    </thead>
    {% endif %}
  <!-- Only display rows that are have an empty "obsolete" field -->
  <!-- manually constructing table -->
  <!-- Institution,Type,RApproval,Initiator,Verifier,Further info,Notes,Examples,Contributed,Lastdate,Obsolete -->
  {% if row["Obsolete"] %}
    <!-- Data for {{ row["Institution"] }} ({{ row["Lastdate"] }}) was obsoleted on {{ row["Obsolete"] }} -->
  {% else %}
  <tr>
    <td> {{ row["Institution"] }} </td>
    <td> {{ row["Type"] }} </td>
    <td> {{ row["RApproval"] }} </td>
    <td> {{ row["Initiator"] }} </td>
    {% if row["Verifier"] %}
      <td> {{ row["Verifier"] }} </td>
      {% else %}
      <td></td>
    {% endif %}
    {% if row["Further info"] %}
      <td> <a href="{{ row["Further info"] }}" alt="Link to additional information">Link</a></td>
      {% else %}
      <td></td>
    {% endif %}
    {% if row["Notes"] %}
      <td> <a href="information/{{ row["Notes"] }}.html" alt="Link to notes">Notes</a></td>
      {% else %}
      <td></td>
    {% endif %}
    <td> {{ row["Examples"] }} </td>
    <td class="contributor">{{ row["Contributed"] }}<br/>{{ row["Lastdate"] }}</td>
  </tr>
  {% endif %}
  {% endfor %}
</table>

## Definitions

## Downloading

To download the entire database in CSV format, [click here](https://raw.githubusercontent.com/social-science-data-editors/reference/main/_data/verifications.csv).

## Adding entries

To add an entry, [click here](https://github.com/social-science-data-editors/reference/edit/main/_data/verifications.csv), and create a pull request.