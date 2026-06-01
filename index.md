---
layout: default
---

# AI Daily Digest

每日 AI 研究、AI Coding、網路技術與 Linux 內核趨勢匯整。

## 最新文章

{% assign now_ts = site.time | date: '%s' | plus: 0 %}
{% assign seven_days_ago = now_ts | minus: 604800 %}

### AI Daily Digest（通用前沿）
<ul>
{% assign daily_pages = site.pages | where_exp: "p", "p.path contains 'daily/'" | sort: "path" | reverse %}
{% assign daily_count = 0 %}
{% for p in daily_pages %}
  {% if p.date %}
    {% assign p_ts = p.date | date: '%s' | plus: 0 %}
    {% if p_ts > seven_days_ago and daily_count < 7 %}
      <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
      {% assign daily_count = daily_count | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}
{% if daily_count == 0 %}
  <li><em>過去 7 天內暫無文章</em></li>
{% endif %}
</ul>

### AI Coding Agents Digest（編程代理專區）
<ul>
{% assign agents_pages = site.pages | where_exp: "p", "p.path contains 'agents/'" | sort: "path" | reverse %}
{% assign agents_count = 0 %}
{% for p in agents_pages %}
  {% if p.date %}
    {% assign p_ts = p.date | date: '%s' | plus: 0 %}
    {% if p_ts > seven_days_ago and agents_count < 7 %}
      <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
      {% assign agents_count = agents_count | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}
{% if agents_count == 0 %}
  <li><em>過去 7 天內暫無文章</em></li>
{% endif %}
</ul>

### Network Daily Digest（網路技術專區）
<ul>
{% assign network_pages = site.pages | where_exp: "p", "p.path contains 'network/'" | sort: "path" | reverse %}
{% assign network_count = 0 %}
{% for p in network_pages %}
  {% if p.date %}
    {% assign p_ts = p.date | date: '%s' | plus: 0 %}
    {% if p_ts > seven_days_ago and network_count < 7 %}
      <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
      {% assign network_count = network_count | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}
{% if network_count == 0 %}
  <li><em>過去 7 天內暫無文章</em></li>
{% endif %}
</ul>

### Linux Kernel Deep Dive（內核專區）
<ul>
{% assign kernel_pages = site.pages | where_exp: "p", "p.path contains 'kernel/'" | sort: "path" | reverse %}
{% assign kernel_count = 0 %}
{% for p in kernel_pages %}
  {% if p.date %}
    {% assign p_ts = p.date | date: '%s' | plus: 0 %}
    {% if p_ts > seven_days_ago and kernel_count < 7 %}
      <li><a href="{{ p.url | relative_url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
      {% assign kernel_count = kernel_count | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}
{% if kernel_count == 0 %}
  <li><em>過去 7 天內暫無文章</em></li>
{% endif %}
</ul>

## 閱讀方式

- [GitHub 倉庫](https://github.com/Aiden128/ai-daily-digest)
- [GitHub Pages](https://Aiden128.github.io/ai-daily-digest/)
