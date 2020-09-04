---
title:  "Research and Academics Glossary"
description: "A short and snappy description referencing the learning outcome and/or breakthrough!"
category: Getting Started with Research
authors:
    - UCLA Undergraduate Research Center&#58; Arts, Humanities, and Social Sciences
    - kian-ravaei
    - doug-worsham
---
<dl class="row">
  {% for entry in site.data.glossary %}
  <dt class="col-sm-3">{{ entry.term }}</dt>
  <dd class="col-sm-9">{{ entry.definition }} <cite>(<a href="{{ entry.reference }}" target="_blank">{{ entry.reference | remove: "http://" | remove: "https://" | remove: "www."}}</a>)</cite></dd>
  {% endfor %}
</dl>

<center>
<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdSe4ujpnDT3wpw4P1U5kk_iUukXdPgkRARR0n22BOxPI9cXg/viewform?embedded=true" width="640" height="400" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
</center>