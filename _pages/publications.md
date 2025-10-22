---
layout: page
permalink: /publications/
title: publications
description: Here you can browse my growing collection of publications.
nav: true
nav_order: 1
---

<style>
  p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h2>Journal Papers</h2>
{% bibliography -q @article %}

<h2>Conference Papers</h2>
{% bibliography -q @inproceedings %}

</div>
