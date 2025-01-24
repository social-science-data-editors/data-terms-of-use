---
title: Additional Trusted Repositories
layout: withtable
---

This list tabulates  repositories that are not have been certified by  [CoreTrustSeal](https://www.coretrustseal.org/), nor appear (at the time of posting here) on other lists of research data repositories ([Nature](https://www.nature.com/sdata/policies/repositories), [F1000Research](https://f1000research.com/for-authors/data-guidelines#hosting),  [PLOS](https://journals.plos.org/plosone/s/data-availability)), but have been 
found to be acceptable for the purpose of archiving social and economic data by data editors.

In order to appear on this list, the repositories must, at the minimum, have an accessible preservation policy. Ideally, they are (correctly) listed on [re3data.org](https://www.re3data.org/), 

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
  <!-- Name,URL,Openness,Assigns DOI,Preservation policy URL,re3data entry,Recommender -->
  <tr>
    <td> {{ row["Name"] }} </td>
    <td> <a href="{{ row["URL"] }}" alt="Link to repository">{{ row["URL"] }}</a></td>
    <td> {{ row["Openness"] }} </td>
    <td> {{ row["Preservation policy URL"] }} </td>
    {% if row["Assigns DOI"] %}
    <td> <a href="{{ row["Assigns DOI"] }}" alt="Link to preservation policy">{{ row["Assigns DOI"] }}</a></td>
    {% else %}
    <td></td>
    {% endif %}
    {% if row["Preservation policy URL"] %}
    <td> <a href="{{ row["re3data entry"] }}" alt="Link to re3data entry">{{ row["re3data entry"] }}</a></td>
    {% else %}
    <td></td>
    {% endif %}
    <td class="Recommender">{{ row["Recommender"] }}</td>
  </tr>
  {% endfor %}
</table>



To download the entire database, [click here](https://raw.githubusercontent.com/social-science-data-editors/reference/main/_data/trusted-repositories.csv).
