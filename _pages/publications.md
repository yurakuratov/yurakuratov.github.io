---
layout: page
permalink: /publications/
title: publications
description: 
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

This page highlights selected publications. For the full list, see my [Google Scholar profile](https://scholar.google.com/citations?user=BsDK7zIAAAAJ&hl=en).

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

<style>
  .copy-bibtex {
    color: var(--global-text-color);
    border: 1px solid var(--global-text-color);
    padding: 0.25rem 1rem;
    margin-left: 0.25rem;
  }

  .copy-bibtex:hover {
    color: var(--global-theme-color);
    border-color: var(--global-theme-color);
  }
</style>

<script>
  (() => {
    const copyText = async (text) => {
      if (navigator.clipboard && window.isSecureContext) {
        await navigator.clipboard.writeText(text);
        return;
      }

      const textarea = document.createElement("textarea");
      textarea.value = text;
      textarea.setAttribute("readonly", "");
      textarea.style.position = "fixed";
      textarea.style.top = "-1000px";
      document.body.appendChild(textarea);
      textarea.select();
      document.execCommand("copy");
      textarea.remove();
    };

    document.querySelectorAll(".publications .links a.bibtex").forEach((bibButton) => {
      const entry = bibButton.closest("[id]");
      const bibBlock = entry?.querySelector(".bibtex.hidden");
      const bibText = bibBlock?.innerText.trim();

      if (!bibText) return;

      const copyButton = document.createElement("button");
      copyButton.type = "button";
      copyButton.className = "copy-bibtex btn btn-sm z-depth-0";
      copyButton.textContent = "Copy Bib";

      copyButton.addEventListener("click", async () => {
        const original = copyButton.textContent;
        try {
          await copyText(bibText);
          copyButton.textContent = "Copied";
        } catch {
          copyButton.textContent = "Copy failed";
        }
        window.setTimeout(() => {
          copyButton.textContent = original;
        }, 1600);
      });

      bibButton.insertAdjacentElement("afterend", copyButton);
    });
  })();
</script>
