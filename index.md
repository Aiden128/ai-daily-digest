---
layout: default
---

# AI Daily Digest

每日 AI 研究、AI Coding、網路技術與 Linux 內核趨勢匯整。

## 最新文章

### AI Daily Digest（通用前沿）
<ul>
{% assign daily_pages = site.pages | where_exp: "p", "p.path contains 'daily/'" | sort: "path" | reverse %}
{% for p in daily_pages limit:30 %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
{% endfor %}
</ul>

### AI Coding Agents Digest（編程代理專區）
<ul>
{% assign agents_pages = site.pages | where_exp: "p", "p.path contains 'agents/'" | sort: "path" | reverse %}
{% for p in agents_pages limit:30 %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
{% endfor %}
</ul>

### Network Daily Digest（網路技術專區）
<ul>
{% assign network_pages = site.pages | where_exp: "p", "p.path contains 'network/'" | sort: "path" | reverse %}
{% for p in network_pages limit:30 %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
{% endfor %}
</ul>

### Linux Kernel Deep Dive（內核專區）
<ul>
{% assign kernel_pages = site.pages | where_exp: "p", "p.path contains 'kernel/'" | sort: "path" | reverse %}
{% for p in kernel_pages limit:30 %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
{% endfor %}
</ul>

## 閱讀方式

- [GitHub 倉庫](https://github.com/Aiden128/ai-daily-digest)
- [GitHub Pages](https://Aiden128.github.io/ai-daily-digest/)
