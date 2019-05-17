<div class="tab-pane active" id="androidstudio" role="tabpanel" aria-labelledby="androidstudio-tab" markdown="1">

## 创建应用程序 {#create-app}

 1. 选择**文件 > 新建Flutter项目**。
 1. 选择**Flutter应用程序**作为项目类型，然后点击**下一步**。
 1. 确保**Flutter SDK路径**文本字段指定SDK的位置。如果尚未安装SDK，请安装它。
 1. 输入项目名（例如`myapp`），然后点击**下一步**。
 1. 点击**完成**。
 1. 等待Android Studio安装SDK，然后创建项目。

上面的命令创建了一个名为`myapp`的Flutter项目目录，其中包含一个使用[Material组件][]的简单演示应用程序。

{% include_relative _main-code-note.md  %}

## 运行应用程序

 1. 找到主Android Studio工具栏：<br>
    ![Main IntelliJ toolbar][]{:.mw-100}
 1. 在**目标选择器**中，选择用于运行应用程序的Android设备。如果没有可用的，请选择**工具 > Android > AVD管理器**并在那里创建一个。 有关详细信息，请参阅[管理AVD][]。
 1. 单击工具栏中的运行图标，或调用菜单项**Run > Run**。

{% capture save_changes -%}
  ：调用**保存所有**，或单击**热重载**
  <i class="material-icons align-bottom">offline_bolt</i>。
  {% comment %} Or, as an alternative:
    {% asset 'get-started/hot-reload-button.png' alt='looks like a lightning bolt' %}.
  {% endcomment -%}
{% endcapture %}

{% capture ide_profile -%}
  调用IDE中的菜单项**Run > Profile**，或
{% endcapture %}

{% include_relative _try-hot-reload.md save_changes=save_changes %}
{% include run-profile.md ide_profile=ide_profile %}

[Main IntelliJ toolbar]: {% asset tools/android-studio/main-toolbar.png @path %}
[管理AVD]: {{site.android-dev}}/studio/run/managing-avds
[Material组件]: {{site.material}}/guidelines
</div>
