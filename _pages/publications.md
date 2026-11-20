---
layout: page
permalink: /publications/
title: Publications
description: Publications by categories in reversed chronological order.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<style>
  .publications .author em {
    color: var(--global-theme-color, #b509ac);
    font-style: normal;
    font-weight: 700;
  }
</style>

<p style="padding: 0.75rem 1rem; border-left: 3px solid var(--global-theme-color, #b509ac); background-color: rgba(181, 9, 172, 0.08); border-radius: 0.25rem;">
  I have <strong style="color: var(--global-theme-color, #b509ac); font-weight: 700;">three additional first-author papers in progress</strong>, with further details available in my <a href="{{ '/cv/' | relative_url }}">CV</a>.
</p>

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

<script>
  // The site-wide max_author_limit is 5; show only the authors up to Yifan Li for this entry.
  document.addEventListener("DOMContentLoaded", function () {
    var author = document.querySelector("#marais2023emissioncontrols .author");
    if (!author) return;
    var shown = ["Eloise A. Marais", "Jamie M. Kelly", "Karn Vohra"];
    var hidden = ["Gongda Lu", "Naila Hina", "Ed C. Rowe"];
    var collapsed = hidden.length + " more authors";
    author.innerHTML = shown.join(", ") + ", <em>Yifan Li</em>, and ";
    var more = document.createElement("span");
    more.className = "more-authors";
    more.title = "click to view " + collapsed;
    more.textContent = collapsed;
    more.addEventListener("click", function () {
      more.title = "";
      more.textContent = more.textContent === collapsed ? hidden.join(", ") : collapsed;
    });
    author.appendChild(more);
  });
</script>
