---
title: "Published Papers"
layout: default
---

# Published Papers

SAILS（Society for AI in Life Sciences）で公開された論文一覧です。

---

{% assign sorted_papers = site.pages | where_exp: "p", "p.path contains 'papers/' and p.path != 'papers/index.md'" | sort: "published" %}

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
