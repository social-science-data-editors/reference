---
title: Verification when data are not publishable
nav_title: Verification
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

### Third-party certification

An independent third-party, not affiliated with either researcher or institution holding the data, conducts the research.

### Institution

The institution holding the data conducts the verification. When the researcher is affiliated with the institution (staff), the verification will be considered *internal*, or possibly *arms-length*. When the researcher is not affilicated with the institution (example: research data centers with external researchers) the verification will be considered *independent*.

### Arms-length replicator

An *arms-length* replicator may be a research assistant employed by the researcher, but not previously involved in the research. Arms-length replicators are expected to follow the same protocols and standards as independent replicators, ensuring objectivity and minimizing potential biases.

### Independent replicator

An *independent* replicator is not affiliated with the researcher, and is normally sent or mandated by the journal's data editor to conduct the research. 

### Approval

In certain cases, the researcher may need to provide approval for others to access or use their research project. In general, journals require researchers to assist journals in this process, but it may be more constraining for verifications conducted after publication. 

### Initiator

The *initiator* is the person or entity who has to trigger the process. In some cases, the journal cannot, on its own, trigger the verification. In others, in particular with **independent** or **third-party** replicators, approval may not be needed by the researcher. Almost always, approval by the entity holding the data will be required, thus, that is not separately broken out in the table.

## Downloading

To download the entire database in CSV format, [click here](https://raw.githubusercontent.com/social-science-data-editors/reference/main/_data/verifications.csv).

## Adding entries

To add an entry, [click here](https://github.com/social-science-data-editors/reference/edit/main/_data/verifications.csv), and create a pull request.