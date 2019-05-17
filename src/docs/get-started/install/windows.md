---
title: Windows安装
short-title: Windows
# js: [{defer: true, url: /assets/archive.js}]
next:
  title: 设置编辑器
  path: /docs/get-started/editor
---

{% assign os = 'windows' -%}

## System requirements

要安装和运行Flutter，您的开发环境必须符合这些最低要求：

- **操作系统**：Windows 7 SP1或更高版本（64位）
- **磁盘空间**：400 MB（不包括IDE/工具的磁盘空间）。
- **工具**：Flutter依赖于您环境中可用的这些工具。
  - [Windows PowerShell 5.0][]或更高版本（Windows 10预装）
  - [Git for Windows][] 2.x，使用**从Windows命令提示符使用Git**选项。

     如果已经安装了Git for Windows，请确保您可以从命令提示符或PowerShell运行`git`命令。

{% include_relative _get-sdk-win.md %}

{% include_relative _android-setup.md %}

## 下一步

[下一步：配置编辑器](/docs/get-started/editor)

[Git for Windows]: https://git-scm.com/download/win
[Windows PowerShell 5.0]: https://docs.microsoft.com/en-us/powershell/scripting/setup/installing-windows-powershell
