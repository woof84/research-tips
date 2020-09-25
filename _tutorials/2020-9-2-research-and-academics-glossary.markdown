---
title:  "Research and Academics Glossary"
description: "A short and snappy description referencing the learning outcome and/or breakthrough!"
category: Getting Started with Research
authors:
    - UCLA Undergraduate Research Center&#58; Arts, Humanities, and Social Sciences
    - kian-ravaei
    - doug-worsham
---
{% assign sorted_documents = site.documents | sort: "title" %}

<!-- search input form -->
<div class="row">
                    <div class="col-lg-12 col-md-12 mx-auto mb-5">
                        <div class="input-group md-form form-sm form-1 pl-0 mb-0">
                          <div class="input-group-prepend">
                            <span class="input-group-text" style="background-color: #005587;" id="basic-text1"><i class="fas fa-search text-white" aria-hidden="true"></i></span>
                            <label for="myInput" class="sr-only">Search</label>
                          </div>
                          <input class="form-control form-control-lg input-lg" id="myInput" type="text" aria-label="Search for tutorials and workshops" placeholder="Search for a term or definition...">
                        </div>
                    </div>
</div>

<!-- list of content in a search table -->
<!-- -->
<!-- -->
<h2>WI+RE Tutorials, Workshops, and Handouts</h2>
 <table class="table table-sm table-responsive-sm">
        <thead>
            <th scope="col" style="display: none;">Thumbnail</th>
            <th scope="col" style="display: none;">Title</th>
            <th scope="col" style="display: none;">Learning Outcomes</th>
            <th scope="col" style="display: none;">Tags</th> <!-- use tags for common search terms, e.g., "lit review" - column is hidden but matching results will still display -->
        </thead>
        <tbody id="myTable">
{% for item in sorted_documents %}
    {% if item.layout != "embed" and item.layout != "embed-simple" and item.layout != "post" and item.layout != "team-member" %}
            {% if item.title %}
                <tr>
                        <td>
                            {% if item.thumbnail %}
                                        <img src="{{ item.thumbnail | relative_url }}" class="img-fluid  d-none d-md-block" style="width: 100px;" alt=""> <!-- decorative img alt intentionally left blank -->
                                    {% else %}
                                        <img src="{{ '/assets/images/icons/tutorial-tn.png' | relative_url }}" class="img-fluid" style="width: 100px;" alt=""><!-- decorative img alt intentionally left blank -->
                                    {% endif %}
                        </td>
                        <td>
                            <p><strong><a href="{{ item.url | relative_url }}">{{ item.title }}</a> {% if item.awards %}{% for award in item.awards %}{% include award-namify.html %} <i aria-hidden="true" class="fas fa-award" data-toggle="tooltip" data-placement="right" title="{{ awardName }}"></i><span class="sr-only">{{ awardName }}</span>{% endfor %}{% endif %}<small><em> ({{ item.layout | capitalize }})</em></small></strong></p>
                        </td>
                        <td style="display: none;">
                                {% if item.learning-outcomes %}
                                    <ul>
                                        {% for outcome in item.learning-outcomes %}
                                            <li>{{ outcome }}</li>
                                        {% endfor %}
                                    </ul>
                                    {% else %}
                                        <small><em>Coming soon!</em></small>
                                {% endif %}
                        </td>
                        <td style="display: none;">
                            {% if item.tags %}
                                <p>{{ item.tags | split: ", " }}</p>
                            {% endif %}
                        </td>
                </tr>
            {% endif %}
    {% endif %}
{% endfor %}
</tbody>
</table>


<hr>

<!--Old Version-->

{% for entry in site.data.glossary %}
<div class="card mt-3 shadow-sm">
  <div class="card-body">
    <h2 class="card-title">{{ entry.term }}</h2>
    <p class="card-text">{{ entry.definition }}</p>
    <div class="btn-group btn-group-sm mb-1 float-right" role="group" aria-label="Actions">
      <a href="#" class="btn btn-primary">Examples</a>
      <a href="#" class="btn btn-primary">Related Resources</a>
      <a href="#" class="btn btn-primary">Reference</a>
    </div>
  </div>
</div>
{% endfor %}


<hr>

<!--Old Version-->

<dl class="row">
  {% for entry in site.data.glossary %}
  <dt class="col-sm-3">{{ entry.term }}</dt>
  <dd class="col-sm-9">{{ entry.definition }} <cite>(<a href="{{ entry.reference }}" target="_blank">{{ entry.reference | remove: "http://" | remove: "https://" | remove: "www."}}</a>)</cite></dd>
  {% endfor %}
</dl>

<center>
<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdSe4ujpnDT3wpw4P1U5kk_iUukXdPgkRARR0n22BOxPI9cXg/viewform?embedded=true" width="640" height="400" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
</center>