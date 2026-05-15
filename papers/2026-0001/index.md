---
title: "論文タイトル（Title of the Paper）"
authors:
  - "著者名1（Affiliation1）"
  - "著者名2（Affiliation2）"
doi: "10.5281/zenodo.xxxxxxx"
published: "2026-01-15"
pdf: "./paper.pdf"
keywords:
  - "keyword1"
  - "keyword2"
  - "keyword3"
---

# {{ page.title }}

## Authors
{% for author in page.authors %}
- {{ author }}
{% endfor %}

## DOI
[{{ page.doi }}](https://doi.org/{{ page.doi }})

## Publication Date
{{ page.published }}

## PDF
[Download PDF](./paper.pdf)

---

## Abstract
ここに要旨（Abstract）を記載します。  
200〜300 words 程度

---

## Citation
以下の形式で引用できます：
\\\著者名（年）. 論文タイトル. SAILS. https://doi.org/xxxxx\\\

---

## Keywords
{% for kw in page.keywords %}
- {{ kw }}
{% endfor %}

