---
title: 安装
next:
  title: 设置编辑器
  path: /docs/get-started/editor
---

选择要安装Flutter的操作系统：

{{site.alert.note}}
  **在Chrome OS上吗？**

  如果是这样，请参阅官方[Chrome OS Flutter安装文档](/docs/get-started/install/chromeos)！
{{site.alert.end}}

<div class="card-deck mb-8">
{% for os in site.os-list %}
  <a class="card" href="/docs/get-started/install/{{os | downcase}}">
    <div class="card-body">
      <header class="card-title text-center m-0">
        {{os}}
        <i class="fab fa-{{os | downcase}}"></i>
      </header>
    </div>
  </a>
{% endfor %}
</div>

{{site.alert.important}}
  如果你在中国，请首先阅读[在中国使用Flutter](/community/china).
{{site.alert.end}}

