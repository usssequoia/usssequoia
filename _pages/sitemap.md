---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: false
entries_layout: "list"
allowed_extensions: [ "htm", "html", "xhtml", "pdf" ]
---

A list of all the posts and pages found on the site. For you robots out there is an [XML version]({{ "sitemap.xml" | relative_url }}) available for digesting as well.

<h1>Pages</h1>

{% assign entries_layout = page.entries_layout | default: 'list' %}
{% assign posts = site.pages | where_exp: "post", "post.hidden != true" | where_exp: "post", "post.sitemap != false" %}
<div class="entries-{{ entries_layout }}">
{% for post in posts %}
  {% comment %}
  This gets the file extension from URL in a pretty low-tech way. Then, it looks for that extension in page.allowed_extensions. If it's not in the list, then we skip this loop iteration.
  {% endcomment %}
  {% assign last_path_elt = post.url | split: "/" | last %}
  {% assign last_path_chr = post.url | slice: -1, 1 %}
  {% if last_path_chr == "/" %}
      {% assign last_path_elt = "index.html" %}
  {% endif %}
  {% assign path_extension = last_path_elt | split: "." | last | downcase %}
  {% assign allowed_extension = page.allowed_extensions | where_exp: "e", "e == path_extension" | default: false %}
  {% unless allowed_extension %}
    {% continue %}
  {% endunless %}
  {% include archive-single.html %}
  <em><a href="{{ post.url }}">({{ post.url }})</a></em>
{% endfor %}
</div>
<br/>
<h1>Documents</h1>

{% assign entries_layout = page.entries_layout | default: 'list' %}
{% assign posts = site.documents | where_exp: "post", "post.hidden != true" | where_exp: "post", "post.sitemap != false" %}
<div class="entries-{{ entries_layout }}">
{% for post in posts %}
  {% comment %}
  This gets the file extension from URL in a pretty low-tech way. Then, it looks for that extension in page.allowed_extensions. If it's not in the list, then we skip this loop iteration.
  {% endcomment %}
  {% assign last_path_elt = post.url | split: "/" | last %}
  {% assign last_path_chr = post.url | slice: -1, 1 %}
  {% if last_path_chr == "/" %}
      {% assign last_path_elt = "index.html" %}
  {% endif %}
  {% assign path_extension = last_path_elt | split: "." | last | downcase %}
  {% assign allowed_extension = page.allowed_extensions | where_exp: "e", "e == path_extension" | default: false %}
  {% unless allowed_extension %}
    {% continue %}
  {% endunless %}
  {% include archive-single.html %}
  <em><a href="{{ post.url }}">({{ post.url }})</a></em>
{% endfor %}
</div>

