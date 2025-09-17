---
layout: page
permalink: /publications/
title: Publications
description: Atmospheric aerosol particles are complex mixtures of organic and inorganic compounds of varying sizes, posing a challenge to accurately represent their formation and growth in models. The primary goal of my research is to advance the understanding of the roles played by heterogeneous and multiphase chemistry in climate and air quality, this involves integrating novel mechanisms into aerosol models.
nav: true
nav_order: 2
years: [2024, 2023, 2022]
sections:
  - bibquery: "@article"
    text: "Peer-reviewed publications"
  - bibquery: "@conference"
    text: "Select conference presentations"
#   - bibquery: "@misc|@phdthesis|@mastersthesis"
#     text: "Thesis"
---

<div class="publications">

{%- for section in page.sections %}
  <a id="{{section.text}}"></a>
  <p class="bibtitle" style="font-weight: bold; font-size: 24px">{{section.text}}</p>
  {%- for y in page.years %}

    {%- comment -%}  Count bibliography in actual section and year {%- endcomment -%}
    {%- capture citecount -%}
    {%- bibliography_count -f {{site.scholar.bibliography}} -q {{section.bibquery}}[year={{y}}] -%}
    {%- endcapture -%}

    {%- comment -%} If exist bibliography in actual section and year, print {%- endcomment -%}
    {%- if citecount !="0" %}

      {% bibliography -f {{site.scholar.bibliography}} -q {{section.bibquery}}[year={{y}}] %}

    {%- endif -%}
    
  {%- endfor %}

{%- endfor %}

</div>