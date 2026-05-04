---
layout: default
---

# AI Daily Digest

每日 AI 研究與 AI Coding 趨勢匯整。

## 最新文章

<ul>
{% assign daily_pages = site.pages | where_exp: "p", "p.path contains 'daily/'" | sort: "path" | reverse %}
{% for p in daily_pages limit:30 %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
{% endfor %}
</ul>

## 閱讀方式

- [GitHub 倉庫](https://github.com/Aiden128/ai-daily-digest)
- [GitHub Pages](https://Aiden128.github.io/ai-daily-digest/)

---


