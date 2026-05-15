---
title: "Published Papers"
layout: default
---

# Published Papers

SAILS（Society for AI in Life Sciences）で公開された論文一覧です。

---

{% comment %}
1. site.pages から papers/ 以下のページを抽出
2. 年フォルダ（2026 など）と番号フォルダ（0001 など）を含むパスだけを対象
3. papers/index.md 自身は除外
{% endcomment %}

{% assign papers = site.pages 
  | where_exp: "p", "p.path contains 'papers/'" 
  | where_exp: "p", "p.path != 'papers/index.md'" 
  | where_exp: "p", "p.path contains '/index.md'" 
%}

{% assign sorted_papers = papers | sort: "published" | reverse %}

{% for paper in sorted_papers %}
## [{{ paper.title }}]({{ paper.url | relative_url }})

**Authors:**  
{% for author in paper.authors %}
- {{ author }}
{% endfor %}

**Published:** {{ paper.published }}

**DOI:**  
[{{ paper.doi }}](https://doi.org/{{ paper.doi }})

---

{% endfor %}
