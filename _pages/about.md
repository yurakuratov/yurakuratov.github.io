---
layout: default
title: Yura Kuratov
permalink: /
description: Personal research website for Yura Kuratov, also known as Yuri, Yury, or Yurii Kuratov.
---

<style>
  .terminal-home {
    max-width: 760px;
    margin: 10vh auto;
    padding: 0 1.25rem;
    font-family:
      ui-monospace,
      SFMono-Regular,
      Menlo,
      Monaco,
      Consolas,
      "Liberation Mono",
      "Courier New",
      monospace;
    font-size: 0.95rem;
    line-height: 1.55;
  }

  body:has(.terminal-home) footer {
    display: none;
  }

  .terminal-home h1 {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 0.25rem;
  }

  .terminal-intro {
    align-items: center;
    display: flex;
    gap: 1.25rem;
  }

  .terminal-photo {
    --photo-scale: 0.9;
    --photo-source-width: 192px;
    --photo-x: 0px;
    --photo-y: 10px;
    background-image: url("{{ '/assets/img/yurakuratov.jpg' | relative_url }}");
    background-position: calc(50% + var(--photo-x)) calc(50% + var(--photo-y));
    background-repeat: no-repeat;
    background-size: calc(var(--photo-source-width) * var(--photo-scale)) auto;
    border: 1px solid var(--global-divider-color);
    border-radius: 6px;
    flex: 0 0 auto;
    height: 192px;
    width: 170px;
  }

  @media (max-width: 520px) {
    .terminal-intro {
      align-items: flex-start;
      flex-direction: column;
      gap: 0.8rem;
    }
  }

  .terminal-home p,
  .terminal-home ul {
    margin-bottom: 0;
  }

  .terminal-home ul {
    list-style: none;
    padding-left: 1.1rem;
  }

  .terminal-home .muted {
    opacity: 0.65;
  }

  .terminal-home a,
  .terminal-home button.terminal-link {
    color: var(--global-theme-color);
    text-decoration: none;
  }

  .terminal-home a:hover,
  .terminal-home button.terminal-link:hover {
    text-decoration: underline;
  }

  .terminal-block {
    margin-top: 1.5rem;
  }

  .terminal-prompt::before {
    content: "> ";
    opacity: 0.55;
  }

  .terminal-link {
    appearance: none;
    background: transparent;
    border: 0;
    cursor: pointer;
    font: inherit;
    padding: 0;
  }

  .terminal-copy {
    border: 1px solid var(--global-divider-color);
    border-radius: 4px;
    background: transparent;
    color: var(--global-text-color);
    cursor: pointer;
    font: inherit;
    margin-left: 0.45rem;
    padding: 0.05rem 0.4rem;
  }

  .terminal-copy:hover {
    border-color: var(--global-theme-color);
    color: var(--global-theme-color);
  }
</style>

<main class="terminal-home" aria-label="Yura Kuratov home">

  <div class="terminal-intro">
    <div class="terminal-photo" role="img" aria-label="Yura Kuratov"></div>
    <div>
      <h1>Yura Kuratov</h1>
      <p>deep learning researcher / memory-augmented models</p>
      <p class="muted">
      I work on memory-augmented neural architectures to address limitations of transformer-based models in long-context processing, sequential computation, and test-time adaptation, while also making memory representations more compact.
      My research also covers external memory for LLMs, including retrieval-augmented generation and knowledge graphs.
      My broader research interests include genomic language models, where long sequences, biological structure, and complex data call for new modeling approaches.
      </p>
    </div>
  </div>

  <!-- <section class="terminal-block" aria-labelledby="bio-heading">
    <p id="bio-heading" class="terminal-prompt">bio</p>
    <ul>
      <li>researcher at [current lab / organization]</li>
      <li>previously worked on recurrent memory transformers, long-context benchmarks, and genomic language models</li>
      <li>co-authored work at NeurIPS, ACL, and other ML/NLP venues</li>
    </ul>
  </section> -->

  <!-- uncomment when bio would be expanded -->
  <!-- <section class="terminal-block" aria-labelledby="research-heading">
    <p id="research-heading" class="terminal-prompt">research</p>
    <ul>
      <li>language models / reasoning / agents / evaluation / efficient training</li>
    </ul>
  </section> -->
  <section id="contact" class="terminal-block" aria-labelledby="contact-heading">
    <p id="contact-heading" class="terminal-prompt">contact</p>
    <ul>
      <li>
        email:
        <span id="canonical-email" data-user="yurakuratov" data-domain="gmail" data-tld="com">yurakuratov [at] gmail [dot] com</span>
        <button id="copy-email" class="terminal-copy" type="button">copy</button>
      </li>
    </ul>
  </section>

  <section class="terminal-block" aria-labelledby="links-heading">
    <p id="links-heading" class="terminal-prompt">links</p>
    <p>
      <a href="https://scholar.google.com/citations?user=BsDK7zIAAAAJ&hl=en" rel="external nofollow noopener" target="_blank">scholar</a>
      /
      <a href="https://github.com/yurakuratov" rel="external nofollow noopener" target="_blank">github</a>
      /
      <a href="https://x.com/yurakuratov" rel="external nofollow noopener" target="_blank">x</a>
      /
      <button id="copy-email-link" class="terminal-link" type="button">email</button>
    </p>
  </section>
</main>

<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Person",
    "@id": "{{ site.url }}{{ site.baseurl }}/#person",
    "name": "Yura Kuratov",
    "alternateName": ["Yuri Kuratov", "Yury Kuratov", "Yurii Kuratov"],
    "givenName": "Yura",
    "familyName": "Kuratov",
    "url": "{{ site.url }}{{ site.baseurl }}/",
    "image": "{{ site.url }}{{ site.baseurl }}/assets/img/yurakuratov.jpg",
    "sameAs": [
      "https://scholar.google.com/citations?user=BsDK7zIAAAAJ",
      "https://github.com/yurakuratov",
      "https://x.com/yurakuratov"
    ]
  }
</script>

<script>
  (() => {
    const emailNode = document.getElementById("canonical-email");
    const copyButtons = [document.getElementById("copy-email"), document.getElementById("copy-email-link")].filter(Boolean);

    if (!emailNode || copyButtons.length === 0) return;

    const email = `${emailNode.dataset.user}@${emailNode.dataset.domain}.${emailNode.dataset.tld}`;

    copyButtons.forEach((button) => {
      button.addEventListener("click", async () => {
        try {
          await navigator.clipboard.writeText(email);
          const original = button.textContent;
          button.textContent = "copied";
          window.setTimeout(() => {
            button.textContent = original;
          }, 1600);
        } catch {
          window.location.hash = "contact";
        }
      });
    });
  })();
</script>
