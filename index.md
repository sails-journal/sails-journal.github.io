---
title: "SAILS: Society for AI in Life Sciences"
layout: default
---

# SAILS  
### *Society for AI in Life Sciences*

AI × 生命科学の研究者が持続可能に活動できる、世界初の学術モデルへ

---

## Mission

Society for AI in Life Sciences（SAILS）は、  
AI 技術を活用した医療・生命科学研究の発展を促進し、  
研究者が持続可能に活動できる **新しい学術モデル** を構築することを目的としています。

従来の学術出版が抱える課題  
— 無償労働、遅い出版、評価の偏り、収益の不透明さ —  
これらを解決するために、SAILS は次の革新的な仕組みを採用します

- **論文1本＝1冊の電子出版モデル（世界初）**  
- **査読の透明化（コメント全開示・明確な採否基準）**  
- **著者・査読者・編集部への収益還元モデル**  
- **従来のIFに加え、読了ページ数・売上・SNS 言及など “実際に読まれた指標” を重視した評価**

SAILS は、研究成果が正当に評価され、  
研究者が持続可能に活動できる未来の学術エコシステムを目指します。

---

## Latest Papers

{% comment %}
papers/ 以下の index.md を持つ論文ページを抽出し、
published でソートして最新3件を取得
{% endcomment %}

{% assign papers = site.pages 
  | where_exp: "p", "p.path contains 'papers/'" 
  | where_exp: "p", "p.path != 'papers/index.md'" 
  | where_exp: "p", "p.path contains '/index.md'" 
%}

{% assign sorted = papers | sort: "published" | reverse %}
{% assign latest = sorted | slice: 0, 3 %}

{% for paper in latest %}
<div class="paper-card">

### <a href="{{ paper.url | relative_url }}">{{ paper.title }}</a>

**著者：** {{ paper.authors | join: ", " }}  
**出版日：** {{ paper.published }}  
**DOI：** <a href="https://doi.org/{{ paper.doi }}">{{ paper.doi }}</a>

**要旨（抜粋）：**  
{{ paper.abstract | truncate: 150 }}

</div>
{% endfor %}

---

## Scope

SAILS はまず **薬学 × AI** を中心領域とします。

- 薬物設計  
- 創薬  
- 薬物動態  
- 毒性予測  
- 医療データ解析  

将来的には、  
**医療AI → 生命科学AI → 科学AI全般** へ段階的に拡張可能な構造を採用しています。

---

## SAILS Architecture  
### *SAILS の全体構造（Publishing × Peer Review × Revenue × Metrics）*

<div class="architecture-box">

**SAILS の学術エコシステムは、以下の 5 つの要素で構成されています：**

1. **Publishing Model（出版）**  
   - 論文1本＝1冊の電子出版  
   - DOI 付与  
   - 即時公開  
   - Versioning（改訂版）

2. **Peer Review（査読）**  
   - 公正・迅速・透明  
   - コメント全開示  
   - 2〜4週間で審査  
   - 査読者に報酬

3. **Revenue Sharing（収益還元）**  
   - 著者 40%  
   - 査読者 30%  （2人なら15％ずつ）
   - 編集部 30%  
   - 読了ページ数・売上に連動

4. **Metrics（評価指標）**  
   - 読了ページ数  
   - 売上  
   - Altmetric  
   - SNS 言及  
   - レビュー  
   - 引用数  
   - Composite Score

5. **Value Proposition（価値）**  
   - 若手研究者が活躍できる  
   - 読まれた分だけ報われる  
   - 無償労働に依存しない  
   - 持続可能な学術モデル

---

### 🔷 全体構造（概念図）

┌──────────────────────────┐
│      Publishing Model     │
│  （論文1本＝電子出版）     │
└───────────┬────────────┘
│
▼
┌──────────────────────────┐
│        Peer Review        │
│   公正・迅速・透明な査読   │
└───────────┬────────────┘
│
▼
┌──────────────────────────┐
│      Revenue Sharing      │
│  著者40 / 査読30 / 編集30 │
└───────────┬────────────┘
│
▼
┌──────────────────────────┐
│          Metrics          │
│ 読了 / 売上 / Altmetric 等 │
└───────────┬────────────┘
│
▼
┌──────────────────────────┐
│    Value Proposition      │
│  研究者が報われる未来へ   │
└──────────────────────────┘

</div>

---

## Publishing Model

SAILS は、従来の「号単位の学会誌」ではなく、  
**論文1本＝1冊の電子書籍として出版する世界初のモデル** を採用します。

- 査読通過後、即電子出版  
- 世界中で販売・閲覧可能  
- DOI を付与し、学術的引用に対応  
- 学会サイト上でジャーナルとして管理  
- 将来的な IF 取得も視野に入れる

---

## Revenue Sharing

電子出版によって得られた収益は、  
**著者・査読者・編集部に分配** されます。

例
- 著者：40%  
- 査読者：30%  （2人なら15％ずつ）
- 編集部：30%  

研究者の無償労働に依存しない、  
**持続可能な学術エコシステム** を構築します。

---

## Latest Published Papers

最新の論文はこちらから閲覧できます

▶ **[Published Papers](./papers/)**

---

## Contact

ご質問・お問い合わせはこちら

▶ **sails.journal.org@gmail.com**

---

<footer>
© 2026 SAILS – Society for AI in Life Sciences
</footer>
