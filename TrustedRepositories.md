---
title: Additional Trusted Repositories
layout: withtable
---

This list tabulates  repositories that are not have been certified by  [CoreTrustSeal](https://www.coretrustseal.org/), nor appear (at the time of posting here) on other lists of research data repositories ([Nature](https://www.nature.com/sdata/policies/repositories), [F1000Research](https://f1000research.com/for-authors/data-guidelines#hosting),  [PLOS](https://journals.plos.org/plosone/s/data-availability)), but have been 
found to be acceptable for the purpose of archiving social and economic data by data editors.

In order to appear on this list, the repositories must, at the minimum, have an accessible preservation policy. Ideally, they are (correctly) listed on [re3data.org](https://www.re3data.org/), Inclusion on the list does NOT imply that any single deposit in these repositories comply with any journal's policies, only that they are preserved in a reasonably long-term fashion, with clear access rules. Some of these repositories may only accept submission from certain researchers - this is noted in the table below. 

> Search the database for any keyword in any field.


<table class="display">
  {% for row in site.data.trusted-repositories %}
    {% if forloop.first %}
    <thead>
    <tr>
      {% for cell in row %}
        {% if forloop.last %}
        <th>{{ cell[0] }}</th>
          {% continue %}
        {% else %}
        <th>{{ cell[0] }}</th>
        {% endif %}
      {% endfor %}
    </tr>
    </thead>
    {% endif %}

  <!-- manually constructing table -->
  <!-- Name,URL,Openness,Preservation policy URL,Assigns DOI,re3data entry,Recommender -->
  <tr>
    <td> {{ row["Name"] }} </td>
    <td> <a href="{{ row["URL"] }}" alt="Link to repository">{{ row["URL"] }}</a></td>
    <td> {{ row["Openness"] }} </td>
    <td> <a href="{{ row["Preservation policy URL"] }}" alt="Link to preservation policy">{{ row["Preservation policy URL"] }} </a></td>
    <td> {{ row["Assigns DOI"] }}</td>
    <td> {{ row["re3data entry"] }}</td>
    <td class="Recommender">{{ row["Recommender"] }}</td>
  </tr>
  {% endfor %}
</table>



To download the entire database, [click here](https://raw.githubusercontent.com/social-science-data-editors/reference/main/_data/trusted-repositories.csv).
