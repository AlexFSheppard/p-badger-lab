---
title: Research
nav:
  order: 1
  tooltip: Published works
---

# {% include icon.html icon="fa-solid fa-microscope" %}Research

Research coming out of our lab utilizes multivariate methods we developed to characterize the emergent genetic signal for human complex traits. Our empirical applications focus on psychiatric disorders, neurodegenerative disorders, and cognitive aging. With that said, our extensive collaborative and international network (highlighted below in interactive network plot) has resulted in partnerships to help apply methods with researchers who bring etiological expertise for a wide-range of outcomes, including heart disease, chronic pain, immune-mediated conditions, and medical outcomes more generally. 

{% include section.html %}

{% include search-box.html %}

{% include search-info.html %}

## Highlighted

{% include citation.html lookup="Mapping the genetic landscape across 14 psychiatric disorders" style="rich" %}

{% include citation.html lookup="Genomic structural equation modelling provides insights into the multivariate genetic architecture of complex traits" style="rich" %}

{% include citation.html doi="doi:10.1038/s41588-025-02269-0" style="rich" %}

{% include section.html %}

{% include webweb.html webweb_json=site.data.webweb width=600 height=600 %}

## Articles Authored by Mentees

{%- assign highlighted_ids = "doi:10.1038/s41586-025-09820-3,doi:10.1038/s41562-019-0566-x,doi:10.1038/s41588-025-02269-0" -%}

{% comment %} First-authored by any lab member other than Andrew Grotzinger. We compare the citation's first author against site.members.name and aliases (case-insensitive). {% endcomment %}
{% assign citations_sorted = site.data.citations | sort: "date" | reverse %}
{% assign prev_year = "" %}
{% for citation in citations_sorted %}
  {% assign cid = citation.id | default: "" | downcase %}
  {% if cid == "" %}
    {% continue %}
  {% endif %}
  {% assign first = citation.authors | first | default: "" %}
  {% assign first_lc = first | downcase %}
  {% if first_lc contains "grotzinger" %}
    {% continue %}
  {% endif %}

  {% comment %} Check member name and each alias individually (previous code joined aliases which prevented matching). {% endcomment %}
  {% assign is_mentee = false %}
  {% for m in site.members %}
    {% assign mname = m.name | default: "" | downcase %}
    {% if mname != "" and first_lc contains mname %}
      {% assign is_mentee = true %}
      {% break %}
    {% endif %}
    {% assign maliases = m.aliases | default: "" %}
    {% if maliases != "" %}
      {% for a in maliases %}
        {% assign a_lc = a | downcase %}
        {% if a_lc != "" and first_lc contains a_lc %}
          {% assign is_mentee = true %}
          {% break %}
        {% endif %}
      {% endfor %}
    {% endif %}
    {% if is_mentee %}
      {% break %}
    {% endif %}
  {% endfor %}

  {% if is_mentee %}
    {% assign year = citation.date | slice: 0,4 %}
    {% if year != "" and year != prev_year %}
<div class="citation-details year-heading">
<span class="citation-date">{{ year }}</span>
</div>
      {% assign prev_year = year %}
    {% endif %}
    {% include citation.html citation=citation style="rich" %}
  {% endif %}
{% endfor %}

{% include section.html %}

## Additional Works

{%- comment -%} Render remaining citations (exclude highlighted and those shown above). {%- endcomment -%}
{% assign prev_year2 = "" %}
{% for citation in citations_sorted %}
  {% assign cid = citation.id | default: "" | downcase %}
  {% if cid == "" %}
    {% continue %}
  {% endif %}

  {% assign first = citation.authors | first | default: "" %}
  {% assign first_lc = first | downcase %}

  {% comment %} Recompute is_lab using per-alias checks (same logic as above) {% endcomment %}
  {% assign is_mentee = false %}
  {% for m in site.members %}
    {% assign mname = m.name | default: "" | downcase %}
    {% if mname != "" and first_lc contains mname %}
      {% assign is_mentee = true %}
      {% break %}
    {% endif %}
    {% assign maliases = m.aliases | default: "" %}
    {% if maliases != "" %}
      {% for a in maliases %}
        {% assign a_lc = a | downcase %}
        {% if a_lc != "" and first_lc contains a_lc %}
          {% assign is_mentee = true %}
          {% break %}
        {% endif %}
      {% endfor %}
    {% endif %}
    {% if is_mentee %}
      {% break %}
    {% endif %}
  {% endfor %}

  {% assign is_andrew = false %}
  {% if first_lc contains "grotzinger" %}
    {% assign is_andrew = true %}
  {% endif %}

  {% if is_mentee and is_andrew == false %}
    {% comment %} already displayed in the 'Papers Authored by Mentees' section {% endcomment %}
    {% continue %}
  {% endif %}

  {% assign year = citation.date | slice: 0,4 %}
  {% if year != "" and year != prev_year2 %}
<div class="citation-details year-heading">
<span class="citation-date">{{ year }}</span>
</div>
    {% assign prev_year2 = year %}
  {% endif %}

  {% include citation.html citation=citation style="rich" %}
{% endfor %}
