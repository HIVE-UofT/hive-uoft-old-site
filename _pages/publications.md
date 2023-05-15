---
layout: default
permalink: /publications/
title: "Publications"
description: 
years: [2023, 2022, 2021, 2020]
---
![]({{ site.url }}{{ site.baseurl }}/images/logo/lab-logo.png){: style="width: 250px; "}

### Featured Publications

<script async src="https://badge.dimensions.ai/badge.js" charset="utf-8"></script>
<script type='text/javascript' src='https://d1bxh8uas1mnw7.cloudfront.net/assets/embed.js'></script>

{% for y in page.years %}
------------------------------------------
<h3 class="year">{{y}}</h3>

{% for paper in site.data.publications %}

{% if y == paper.year %}
<div id = "{{paper.title | replace: ' ', '-' | remove: '.' }}" class="clearfix" width="100%" style="padding-top: 5px; padding-bottom: 5px; clear: both;">
<img style="float: left; width: 25%; padding-right: 20px; padding-bottom:40px;" src="{{ paper.image | prepend: '/images/pubpics/' | prepend: site.baseurl | prepend: site.url }}" alt="publication image {% if paper.imagealt %}- {{paper.imagealt}}{% endif %}"> 
<div valign="top" style="overflow: hidden" class="pub">
  {{paper.authors | markdownify | remove: '<p>' | remove: '</p>'}}{% if paper.url %}<a href="{{paper.url}}" target="_blank">{{paper.title}}</a>{% elsif paper.file %}
<a href="{{ paper.file | prepend: '/files/pubpdfs/' | prepend: site.baseurl | prepend: site.url }}" target="_blank">{{paper.title}}</a>
  {% else %}{{paper.title}}{% endif %} {{ paper.details | markdownify | remove: '<p>' | remove: '</p>'}}
{% if paper.github %}<i class="fab fa-github fa-fw"></i> <a href="{{paper.github}}" target="_blank">GitHub</a>{% endif %}  {% if paper.file %}<i class="far fa-solid fa-file-pdf"></i> <a href="{{ paper.file | prepend: '/files/pubpdfs/' | prepend: site.baseurl | prepend: site.url }}" target="_blank">{{paper.filetype}}</a> {% endif %}{% if paper.openmaterials %}<i class="far fa-solid fa-eye"></i> <a href="{{paper.openmaterials}}" target="_blank">Materials</a><br>{% endif %}   {% if paper.opendata %}<i class="fas fa-solid fa-database"></i> <a href="{{paper.opendata}}" target="_blank">Open Data</a><br>{% endif %}
  {% if paper.doi %}
<span class="__dimensions_badge_embed__" data-doi="{{paper.doi}}" data-style="large_rectangle" data-hide-zero-citations="true" data-legend="never"></span><script async src="https://badge.dimensions.ai/badge.js" charset="utf-8"></script> 
<div data-badge-popover="right" data-badge-type="1" data-doi="{{paper.doi}}" data-hide-no-mentions="true" class="altmetric-embed"></div>
  </div><div style="display: table-row; height: 10px"></div>
  {% elsif paper.pmid %}
  <div style="display: table-cell;" class="__dimensions_badge_embed__" data-pmid="{{paper.pmid}}" data-hide-zero-citations="true" data-legend="hover-right" data-style="small_circle"></div> <div style="display: table-cell;" data-badge-popover="right" data-badge-type="donut" data-pmid="{{paper.pmid}}" data-hide-no-mentions="true" class="altmetric-embed"></div>
  </div><div style="display: table-row; height: 22px"></div>
  </div>
  {% endif %}
    
</div>

{% endif %}
{% endfor %}
{% endfor %}

