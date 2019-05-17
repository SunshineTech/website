应用构建完成后，您将在设备上看到启动应用。

{% include app-figure.md img-class="site-mobile-screenshot border"
    path-prefix="get-started" platform="iOS" image="starter-app.png"
    caption="Starter app" %}

## 尝试热重装

Flutter使用_热重载_提供快速开发周期，能够重新加载实时运行的应用程序的代码，而无需重新启动或丢失应用程序状态。更改应用程序源代码，告诉IDE或命令行工具您要热重载，并查看模拟器、仿真器或设备中的更改。

 1. 打开`lib/main.dart`。
 1. 将字符串

    {% prettify dart %}
      'You have [[strike]]pushed[[/strike]] the button this many times'
    {% endprettify %}

    更改为

    {% prettify dart %}
      'You have [!clicked!] the button this many times'
    {% endprettify %}

    {{site.alert.important}}
      _不要_停止你的应用程序。让它运行。
    {{site.alert.end}}

 1. 保存您的更改{{include.save_changes}}

您几乎可以立即在正在运行的应用程序中看到更新的字符串。
