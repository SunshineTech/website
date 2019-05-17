<div class="tab-pane" id="vscode" role="tabpanel" aria-labelledby="vscode-tab" markdown="1">

## 创建应用程序

  1. 调用**视图 > 命令选项板**。
  1. 输入“flutter”，然后选择**Flutter：新建项目**。
  1. 输入项目名（例如`myapp`），然后按**Enter**。
  1. 为新项目文件夹创建或选择父目录。
  1. 等待项目创建完成，和`main.dart`文件显示。

上面的命令创建了一个名为`myapp`的Flutter项目目录，其中包含一个使用[Material组件][]的简单演示应用程序。

{% include_relative _main-code-note.md  %}

## 运行应用程序

 1. 找到VS Code状态栏（窗口底部的蓝色栏）：<br> ![status bar][]{:.mw-100}
 1. 从**设备选择器**区域选择一个设备。有关详细信息，请参阅[快速切换Flutter设备][]。
    - 如果没有可用的设备且您想使用设备模拟器，请单击**无设备**并启动模拟器。
    - 要设置真实设备，请按照[安装][]页面上操作系统的设备特定说明进行操作。
 1. 调用**调试 > 开始调试**或按<kbd>F5</kbd>。
 1. 等待应用程序启动&mdash;进度打印在**调试控制台**视图中。

{% capture save_changes -%}
  ：调用**保存所有**，或单击**热重载**
  <i class="material-icons align-bottom">offline_bolt</i>。
  {% comment %} Or, as an alternative:
    {% asset 'get-started/hot-reload-button.png' alt='looks like a lightning bolt' %}.
  {% endcomment -%}
{% endcapture %}

{% include_relative _try-hot-reload.md save_changes=save_changes %}
{% include run-profile.md %}

[安装]: /docs/get-started/install
[Material组件]: {{site.material}}/guidelines
[快速切换Flutter设备]: https://dartcode.org/docs/quickly-switching-between-flutter-devices
[status bar]: {% asset tools/vs-code/device_status_bar.png @path %}

</div>
