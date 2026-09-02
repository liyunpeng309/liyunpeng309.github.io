{% assign is_zh = page.lang | default: "" %}
<h2 id="publications" style="margin: 2px 0px -15px;">{% if is_zh contains "zh" %}论文发表{% else %}Publications{% endif %}</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image | relative_url }}" class="teaser img-fluid z-depth-1" alt="{{ link.title }} teaser">
    {% if link.conference_short %} 
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      {% assign primary_link = link.pdf %}
      <div class="title">
        {% if primary_link %}
        <a href="{{ primary_link }}" target="_blank" rel="noopener">{{ link.title }}</a>
        {% else %}
        {{ link.title }}
        {% endif %}
      </div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">PDF</a>
      {% endif %}
      {% assign github_link = link.github %}
      {% if github_link == nil %}
        {% if link.code contains 'github.com' %}
        {% assign github_link = link.code %}
        {% endif %}
      {% endif %}
      {% if github_link %}
      <a href="{{ github_link }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">GitHub</a>
      {% endif %}
      {% assign huggingface_link = link.huggingface | default: link.hugging_face %}
      {% if huggingface_link %}
      <a href="{{ huggingface_link }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Hugging Face</a>
      {% endif %}
      {% assign note_type = link.notes | downcase %}
      {% if note_type == 'poster' or note_type == 'oral' %} 
      <strong> <i style="color:#e74d3c">{{ link.notes }}</i></strong>
      {% endif %}
    </div>
  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>
