---
title: "論文タイトル（Title of the Paper）"
authors:
  - "著者名1（Affiliation1）"
  - "著者名2（Affiliation2）"
doi: "10.5281/zenodo.xxxxxxx"
published: "2026-01-15"
paper_id: "2026/0001"
pdf: "./paper.pdf"
ebook_url: "./paper.pdf"   # EPUB や販売ページがあれば差し替え
keywords:
  - "keyword1"
  - "keyword2"
  - "keyword3"
abstract: |
  ここに要旨（Abstract）を記載します。
  200〜300 words 程度。
layout: default
---

# {{ page.title }}

<div class="paper-card">

## 📌 Basic Information

**論文番号：** {{ page.paper_id }}  
**著者：** {{ page.authors | join: ", " }}  
**出版日：** {{ page.published }}  

**DOI：**  
<a href="https://doi.org/{{ page.doi }}">{{ page.doi }}</a>

**PDF：**  
- <a href="{{ page.pdf }}">Download PDF</a>

**電子書籍（eBook）：**  
- <a href="{{ page.ebook_url }}">PDF / EPUB / 販売ページ</a>

---

## 📝 Abstract

{{ page.abstract }}

---

## 🔑 Keywords
{% for kw in page.keywords %}
- {{ kw }}
{% endfor %}

---

## 📚 Citation

以下の形式で引用できます：
```
{{ page.authors | join: ", " }} ({{ page.published | date: "%Y" }}).
{{ page.title }}. SAILS.
https://doi.org/{{ page.doi }}
```

---

## 📦 BibTeX

```
@article{sails_{{ page.paper_id | replace: "/", "_" }},
title   = "{{ page.title }}",
author  = "{{ page.authors | join: " and " }}",
journal = "SAILS",
year    = "{{ page.published | date: "%Y" }}",
doi     = "{{ page.doi }}"
}
```


</div>

<footer>
© 2026 SAILS – Society for AI in Life Sciences
</footer>
