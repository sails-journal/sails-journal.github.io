---
title: "Published Papers"
layout: default
---

# Published Papers  
### *SAILS Journal – 論文一覧*

SAILS では、論文1本＝1冊の電子書籍として出版する  
**Single-Paper Publishing Model** を採用しています。

論文は **年 / 通し番号（例：2026/0001）** で管理され、  
査読通過後すぐに電子出版されます。

---

{% comment %}
1. papers/ 以下の index.md を持つ論文ページを抽出
2. papers/index.md 自身は除外
3. published フロントマターでソート
{% endcomment %}

{% assign papers = site.pages 
  | where_exp: "p", "p.path contains 'papers/'" 
  | where_exp: "p", "p.path != 'papers/index.md'" 
  | where_exp: "p", "p.path contains '/index.md'" 
%}

{% assign sorted_papers = papers | sort: "published" | reverse %}

{% assign current_year = "" %}

{% for paper in sorted_papers %}

  {% assign year = paper.published | date: "%Y" %}

  {% if year != current_year %}
  ## 📘 {{ year }}
  {% assign current_year = year %}
  {% endif %}

<div class="paper-card">

### <a href="{{ paper.url | relative_url }}">{{ paper.title }}</a>

**論文番号：** {{ paper.paper_id }}  
**著者：** {{ paper.authors | join: ", " }}  
**出版日：** {{ paper.published }}  
**DOI：**  
<a href="https://doi.org/{{ paper.doi }}">{{ paper.doi }}</a>

---

**要旨（Abstract）：**  
{{ paper.abstract | truncate: 300 }}

📄 **電子書籍：**  
{% if paper.pdf %}
- <a href="{{ paper.pdf }}">PDF</a>
{% endif %}
{% if paper.epub %}
- <a href="{{ paper.epub }}">EPUB</a>
{% endif %}
{% if paper.ebook_url %}
- <a href="{{ paper.ebook_url }}">販売ページ</a>
{% endif %}


</div>

{% endfor %}

<footer>
© 2026 SAILS – Society for AI in Life Sciences
</footer>
