---
layout: page
title: "Wikontic: Constructing Wikidata-Aligned, Ontology-Aware Knowledge Graphs with Large Language Models"
description: Building ontology-verified knowledge graphs from text using LLMs.
importance: 2
category: project
permalink: /research/wikontic/
img: /assets/img/wikontic/wikontic-pipeline.png
github: https://github.com/screemix/Wikontic
related_publications: false
venue: EACL 2026
authors:
  - Alla Chepurova
  - Aydar Bulatov
  - Mikhail Burtsev
  - Yuri Kuratov
_styles: |
  .paper-meta {
    margin: -0.55rem 0 1.35rem;
    color: var(--global-text-color-light);
    line-height: 1.45;
  }

  .paper-authors {
    display: flex;
    flex-wrap: wrap;
    gap: 0.15rem 0.45rem;
    font-size: 0.98rem;
  }

  .resource-links {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem 1.15rem;
    margin: 0.25rem 0 1.35rem;
  }

  .resource-links a {
    border-bottom: 1px solid var(--global-divider-color);
    color: var(--global-theme-color);
    font-size: 1rem;
    line-height: 1.5;
    text-decoration: none;
  }

  .resource-links a:hover {
    border-bottom-color: var(--global-hover-color);
    color: var(--global-hover-color);
    text-decoration: none;
  }
  
  .paper-venue {
    margin-top: 0.25rem;
    color: var(--global-text-color);
    font-size: 0.9rem;
    font-weight: 500;
  }
---

<div class="paper-meta">
  <div class="paper-authors" aria-label="Paper authors">
    {% for author in page.authors %}
      <span>{{ author }}</span>{% unless forloop.last %}<span aria-hidden="true">·</span>{% endunless %}
    {% endfor %}
  </div>
  {% if page.venue %}
    <div class="paper-venue">{{ page.venue }}</div>
  {% endif %}
</div>

<div class="resource-links">
  <a href="https://aclanthology.org/2026.eacl-long.388/">Paper</a>
  <a href="https://github.com/screemix/Wikontic">Code</a>
  <a href="https://wikontic.deeppavlov.ai">Demo</a>
  <a href="https://github.com/screemix/Wikontic/blob/main/tutorial.ipynb">Tutorial</a>
</div>

Wikontic converts unstructured text into structured knowledge graphs {% cite chepurova-etal-2026-wikontic %}. It uses an ontology to control how extracted knowledge is represented: which entity types are allowed, which relations are valid, and how facts should fit together.

The pipeline extracts candidate `(subject, relation, object)` triplets, refines entities and relations, validates them against an Ontology (we use ontology from WikiData), and stores the resulting graph for retrieval, question answering, visualization, and any other use cases.

<img src="{{ '/assets/img/wikontic/wikontic-pipeline.png' | relative_url }}" alt="Wikontic pipeline for extracting, ontology-aligning, and refining knowledge graphs from text." class="img-fluid d-block mx-auto rounded z-depth-1" style="width: 90%;">

## What It Does

- Extracts candidate triplets from raw text with an LLM.
- Aligns and normalizes entities and relations using constraints from Wikidata ontology.
- Supports both ontology-aware and ontology-free modes, can adapt to Wikidata-like ontologies, and has [LangChain](https://github.com/screemix/Wikontic/blob/main/tutorial.ipynb) integration.
- Supports English and Russian languages.

## Results

- On MuSiQue, the correct answer entity appears in 96% of generated triplets.
- In triplets-only QA (without original context), Wikontic reaches 76.0 F1 on HotpotQA and 59.8 F1 on MuSiQue.
- On MINE-1, it reaches 86% information retention.
- KG construction uses about 3x fewer tokens than AriGraph and under 1/20 of GraphRAG.

## Citation

<div class="publications">
{% bibliography --cited_in_order --file papers --group_by none %}
</div>
