---
title: 在中国使用Flutter
description: 在哪里可以找到本地化为简体中文的Flutter站点的版本。
toc: true
---

{% assign path = 'flutter_infra/releases/stable/windows/flutter_windows_v1.0.0-stable.zip' -%}

Flutter社区已经在网站[https://flutter-io.cn](https://flutter-io.cn)提供了Flutter站点的简体中文版本。

如果您要使用[安装包](/docs/development/tools/sdk/archive)安装Flutter，则可以使用受信任的镜像替换cURL的域名以加快速度。例如：

* 安装包URL：<br>
  [`https://storage.googleapis.com/{{path}}`](https://storage.googleapis.com/{{path}})

* 镜像URL：<br>
  [`https://storage.flutter-io.cn/{{path}}`](https://storage.flutter-io.cn/{{path}})

您还必须设置两个环境变量来在中国升级Flutter并使用pub包存储库。说明如下。

{{site.alert.important}}
  仅当你_信任_提供者时才使用镜像站点。Flutter团队无法验证其可靠性或安全性。
{{site.alert.end}}

## 配置Flutter使用镜像站点

如果您在中国安装或使用Flutter，使用托管Flutter依赖项的可靠本地镜像站点可能会有所帮助。要指示Flutter工具使用备用存储位置，您需要在运行`flutter`命令之前设置两个环境变量`PUB_HOSTED_URL`和`FLUTTER_STORAGE_BASE_URL`。

以MacOS或Linux为例，以下是使用镜像站点的设置过程中的前几个步骤。在Bash shell中，从您希望存储本地Flutter克隆的目录中运行以下命令：


```terminal
$ export PUB_HOSTED_URL=https://pub.flutter-io.cn
$ export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
$ git clone -b dev {{site.github}}/flutter/flutter.git
$ export PATH="$PWD/flutter/bin:$PATH"
$ cd ./flutter
$ flutter doctor
```

完成这些步骤后，您应该能够继续正常[设置Flutter](/docs/get-started/editor)。
从这里开始，`flutter packages get`获取的软件包将在任何设置了`PUB_HOSTED_URL`和`FLUTTER_STORAGE_BASE_URL`的shell中从`flutter-io.cn`下载。

`flutter-io.cn`服务器是[GDG China]()维护的Flutter依赖项和包的临时镜像。Flutter团队无法保证此服务的长期可用性。如果可用，您可以自由使用其他镜像。如果您有兴趣在中国设置自己的镜像，请联系[flutter-dev@googlegroups.com](mailto:flutter-dev@googlegroups.com)寻求帮助。

## 社区运行的镜像站点

* 上海交通大学Linux用户组
  * `FLUTTER_STORAGE_BASE_URL`: [https://mirrors.sjtug.sjtu.edu.cn/](https://mirrors.sjtug.sjtu.edu.cn)
  * `PUB_HOSTED_URL`: [https://dart-pub.mirrors.sjtug.sjtu.edu.cn/](https://dart-pub.mirrors.sjtug.sjtu.edu.cn)
