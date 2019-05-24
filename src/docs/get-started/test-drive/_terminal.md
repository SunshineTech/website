<div class="tab-pane" id="terminal" role="tabpanel" aria-labelledby="terminal-tab" markdown="1">

## 创建应用程序

使用`flutter create`命令创建新项目：

```terminal
$ flutter create myapp
$ cd myapp
```

上面的命令创建了一个名为`myapp`的Flutter项目目录，其中包含一个使用[Material组件]({{site.material}}/guidelines/)的简单演示应用程序。

{% include_relative _main-code-note.md  %}

## 运行应用程序

 1. 检查Android设备是否正在运行。如果未显示，请按照[安装][]页面上操作系统的设备特定说明进行操作。

    ```terminal
    $ flutter devices
    ```

 2. 使用以下命令运行应用程序：

    ```terminal
    $ flutter run
    ```

{% capture save_changes -%}
.
1. 在终端窗口中输入<kbd>r</kbd>。
{% endcapture %}

{% include_relative _try-hot-reload.md save_changes=save_changes %}
{% include run-profile.md %}

[安装]: /docs/get-started/install
</div>
