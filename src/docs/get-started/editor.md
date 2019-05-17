---
title: 设置编辑器
prev:
  title: 安装
  path: /docs/get-started/install
next:
  title: 试驾
  path: /docs/get-started/test-drive
toc: false
---

您可以使用任何文本编辑器结合我们的命令行工具使用Flutter构建应用程序。但是，我们建议使用我们的编辑器插件之一，以获得更好的体验。这些插件为您提供代码完成，语法突出显示，窗口小部件编辑辅助，运行和调试支持等。

按照以下步骤为Android Studio，IntelliJ或VS Code添加编辑器插件。如果您想使用其他编辑器，那没问题，请跳到[下一步：试驾](/docs/get-started/test-drive)。

{% comment %} Nav tabs {% endcomment -%}
<ul class="nav nav-tabs" id="editor-setup" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="androidstudio-tab" href="#androidstudio" role="tab" aria-controls="androidstudio" aria-selected="true">Android Studio / IntelliJ</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="vscode-tab" href="#vscode" role="tab" aria-controls="vscode" aria-selected="false">Visual Studio Code</a>
  </li>
</ul>

{% comment %} Tab panes {% endcomment -%}
<div class="tab-content">

<div class="tab-pane active" id="androidstudio" role="tabpanel" aria-labelledby="androidstudio-tab" markdown="1">

## 安装Android Studio

Android Studio为Flutter提供了完整的集成IDE体验。

* [Android Studio]({{site.android-dev}}/studio) 3.0或更高版本

或者，您也可以使用IntelliJ：

* [IntelliJ IDEA社区版](https://www.jetbrains.com/idea/download/) 2017.1或更高版本
* [IntelliJ IDEA旗舰版](https://www.jetbrains.com/idea/download/) 2017.1或更高版本

## 安装Flutter和Dart插件

要安装这些：

 1. 启动Android Studio。
 1. 打开插件首选项（macOS上的**首选项 > 插件**，Windows和Linux上的**文件 > 设置 > 插件**）。
 1. 选择**浏览存储库**，选择Flutter插件并单击**安装**。
 1. 提示安装Dart插件时单击**是**。
 1. 提示时单击**重启**。

</div>
<div class="tab-pane" id="vscode" role="tabpanel" aria-labelledby="vscode-tab" markdown="1">

## 安装VS Code

VS Code是一个轻量级编辑器，具有Flutter应用程序执行和调试支持。

* [VS Code](https://code.visualstudio.com/)最新稳定版

## 安装Flutter和Dart插件

 1. 启动VS Code。
 1. 调用**视图 > 命令选项板....**。
 1. 输入“install”，然后选择**Extensions: Install Extensions**。
 1. 在扩展搜索字段中键入“flutter”，在列表中选择**Flutter**，然后单击**Install**。这也安装了所需的Dart插件。

## 使用Flutter Doctor验证您的设置

 1. 调用**视图 > 命令选项板....**。
 1. 输入“doctor”，然后选择**Flutter: Run Flutter Doctor**。
 1. 检查**OUTPUT**窗格中的输出是否存在任何问题。

</div>

</div>{% comment %} End: Tab panes. {% endcomment -%}

## 下一步

试驾Flutter：创建第一个项目，运行它，体验“热重载”。
