---
title:  "Research and Academics Glossary"
description: "A short and snappy description referencing the learning outcome and/or breakthrough!"
category: Getting Started with Research
---
<dl class="row">
  {% for entry in site.data.glossary %}
  <dt class="col-sm-3">{{ entry.term }}</dt>
  <dd class="col-sm-9">{{ entry.definition }} <cite>(<a href="{{ entry.reference }}" target="_blank">{{ entry.reference }}</a>)</cite></dd>
  {% endfor %}
</dl>
