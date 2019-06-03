---
title: FAQ
description: 常见问题和解答。
---

## 介绍

### Flutter是什么？

Flutter是Google的便携式UI工具包，用于在创纪录的时间内为移动，Web和桌面制作高质量的本机体验。Flutter与现有代码一起使用，由世界各地的开发人员和组织使用，并且是免费和开源的。

### Flutter做什么？

对于用户来说，Flutter让美丽的应用UI变得生动。

对于开发人员来说，Flutter降低了构建移动应用程序的门槛。它加速了移动应用程序的开发，降低了iOS和Android应用程序生产的成本和复杂性。

对于设计师而言，Flutter有助于提供原始设计愿景，而不会失去保真度或妥协。它还可以作为一种高效的原型工具。

### Flutter适用于谁？

Flutter适用于希望以更快的方式构建漂亮的移动应用程序，或者通过单一投资的方式吸引更多用户的 _开发人员_。

Flutter也适用于需要领导移动开发团队的 _工程经理_。Flutter允许工程经理创建一个 _移动应用开发团队_，统一他们的开发投资，以更快地发布更多功能，同时将相同的功能集发送到iOS和Android，并降低维护成本。

虽然不是最初的目标受众，但Flutter也适用于希望他们的原始设计愿景能够以高保真度向所有移动用户一致提供的 _设计师_。

从根本上说，Flutter适用于需要漂亮的应用程序，令人愉快的动作和动画以及具有个性和身份的UI的用户。

### 我必须要有怎样的程序员/<wbr>开发人员经验才能使用Flutter？

对于熟悉面向对象概念（类，方法，变量等）和命令式编程概念（循环，条件等）的程序员来说，Flutter是平易近人的。

学习和使用Flutter，无需先前的移动经验。

我们已经看到编程经验很少的人学习并使用Flutter进行原型设计和应用程序开发。

### 我可以用Flutter构建哪些类型的应用程序？

Flutter针对想要在Android和iOS上运行的2D移动应用进行了优化。

需要提供品牌优先设计的应用特别适合Flutter。但是，需要看起来像股票平台应用程序的应用程序也可以使用Flutter构建。

您可以使用Flutter构建功能齐全（包括摄像头，地理位置，网络，存储，第三方SDK等）的应用程序。

### 谁制作了Flutter？

Flutter是一个开源项目，由Google和社区提供。

### 谁使用Flutter？

Google内部和外部的开发人员使用Flutter为iOS和Android构建精美的原生应用。 要了解其中一些应用，请访问[展示](/showcase)。

### 什么让Flutter与众不同？

Flutter与构建移动应用程序的大多数其他选项不同，因为Flutter既不使用WebView，也不使用设备附带的OEM小部件。相反，Flutter使用自己的高性能渲染引擎来绘制小部件。

另外，Flutter是不同的，因为它只有一层薄薄的C/C++代码。Flutter以 _Dart_（一种现代，简洁，面向对象的语言）中实现其系统的大部分（合成，手势，动画，框架，小部件等），开发人员可以轻松地进行读取、更改、替换或删除。这为开发人员提供了对系统的巨大控制，同时显著降低了大多数系统的可接近性门槛。

### 我应该用Flutter构建我的下一个生产应用程序吗？

Flutter 1.0于2018年12月4日推出。数以千计的应用程序已随Flutter一起运送到运送到数亿台设备上。请查看[展示](/showcase)中的一些示例应用程序。

有关启动和后续版本的更多信息，请参阅[Flutter 1.0：Google的便携UI工具包](https://developers.googleblog.com/2018/12/flutter-10-googles-portable-ui-toolkit.html)。

## Flutter提供什么？

### Flutter SDK里面有什么？

* 对文本具有出色支持、高度优化、移动优先的2D渲染引擎
* 现代反应式框架
* 适用于Android和iOS的丰富小部件
* 用于单元和集成测试的API
* 连接系统和第三方SDK的互操作和插件API
* 用于在Windows、Linux和Mac上运行测试的无头测试运行器
* 用于创建，构建，测试和编译应用程序的命令行工具

### Flutter可以与任何编辑器或IDE一起使用吗？

我们支持[Android Studio]({{site.android-dev}}/studio)，
[IntelliJ IDEA](https://www.jetbrains.com/idea/)和
[VS Code](https://code.visualstudio.com/)的插件。

有关设置详细信息，请参阅[编辑器配置](/docs/get-started/editor)；有关如何使用插件的提示，请参阅[在IDE中开发Flutter应用程序](/docs/development/tools/android-studio)。

或者，您可以组合使用终端中的`flutter`命令和支持[编辑Dart]({{site.dart-site}}/tools)的众多编辑器之一。

### Flutter是否带有框架？

是的! Flutter附带了灵感来自React的现代框架。Flutter的框架旨在分层和可定制（和可选）。开发人员可以选择仅使用框架的一部分或不同的框架。

### Flutter是否带有小部件？

是的！Flutter附带了一套高品质的Material Design和Cupertino（iOS风格）[小部件][widgets]，布局和主题。当然，这些小部件只是一个起点。Flutter旨在使您可以轻松创建自己的小部件，或自定义现有小部件。

### Flutter是否支持Material主题？

是的！Flutter和Material团队密切合作，完全支持Material主题。[MDC-103 Flutter：Material主题]({{site.codelabs}}/codelabs/mdc-103-flutter)代码实验室中展示了许多这样的例子。

### Flutter是否带有测试框架？

是的，Flutter提供了编写单元和集成测试的API。请了解更多关于[测试Flutter](/docs/testing)的信息。

我们使用自己的测试功能来测试我们的SDK。我们测量每次提交的[测试覆盖](https://coveralls.io/github/flutter/flutter?branch=master)。

### Flutter是否带有依赖注入框架或解决方案？

目前还没有。请通过[{{site.email}}](mailto:{{site.email}})分享您的想法。

## 技术

### Flutter是用什么技术构建的？

Flutter是使用C，C++，Dart和Skia（2D渲染引擎）构建的。请参阅此
[体系结构图](https://docs.google.com/presentation/d/1cw7A4HbvM_Abv320rVgPVGiUP2msVs7tfGbkgdrTy0I/edit#slide=id.gbb3c3233b_0_162)
以获得主要组件的更好图片。

### Flutter如何在Android上运行我的代码？ {#run-android}

引擎的C和C++代码使用Android的NDK编译。Dart代码（SDK和你的）都是提前（AOT）编译到本机的ARM和x86库中。这些库包含在“runner” Android项目中，整个内容都构建在APK中。启动时，应用程序会加载Flutter库。任何呈现，输入或事件处理等都委托给已编译的Flutter和应用程序代码。这类似于许多游戏引擎的工作方式。

调试模式构建使用虚拟机（VM）来运行Dart代码（因此它们显示的“调试”横幅以提醒人们它们稍慢）以便启用有状态热重载。

### Flutter如何在iOS上运行我的代码？ {#run-ios}

引擎的C和C++代码使用LLVM编译。Dart代码（SDK和您的）都是提前（AOT）编译到本机ARM库中。该库包含在“runner” iOS项目中，整个内容都构建在`.ipa`中。启动时，应用程序会加载Flutter库。任何呈现，输入或事件处理等都委托给已编译的Flutter和应用程序代码。这类似于许多游戏引擎的工作方式。

调试模式构建使用虚拟机（VM）来运行Dart代码（因此它们显示的“调试”横幅以提醒人们它们稍慢）以便启用有状态热重载。

### Flutter是否使用我系统的OEM小部件？

不使用。相反，Flutter提供了一组小部件（包括Material Design和Cupertino（iOS风格）小部件），由Flutter的框架和引擎管理和呈现。您可以浏览[Flutter小部件的目录](/docs/development/ui/widgets)。

我们希望最终结果将是更高质量的应用程序。如果我们重用OEM小部件，那么Flutter应用程序的质量和性能将受到这些小部件质量的限制。

例如，在Android中，有一组硬编码的手势和固定的规则来消除它们的歧义。在Flutter中，您可以编写自己的手势识别器，它是[手势系统](/docs/development/ui/advanced/gestures)中的一流参与者。此外，由不同人创作的两个小部件可以协调以消除手势的歧义。

现代应用程序设计趋势指向想要更多动感丰富的UI和品牌优先设计的设计师和用户。为了实现这种级别的定制，美观的设计，Flutter的架构是驱动像素而不是OEM小部件。

通过使用相同的渲染器，框架和一组小部件，可以更轻松地同时发布iOS和Android，而无需仔细和昂贵的计划来对齐两个单独的代码库和功能集。

通过使用单一语言，单个框架和一组用于所有UI的库（无论您的UI对于每个移动平台是不同的还是基本一致），我们还旨在帮助降低应用开发和维护成本。

### 当我的移动操作系统更新并引入新的小部件时会发生什么？

Flutter团队关注iOS和Android新移动小部件的采用和需求，旨在与社区合作构建对新小部件的支持。这项工作可能以低级框架功能，新的可组合小部件或新的小部件实现的形式出现。

Flutter的分层架构旨在支持众多小部件库，我们鼓励并支持社区构建和维护小部件库。

### 当我的移动操作系统更新并引入新平台功能时会发生什么？

Flutter的互操作和插件系统旨在使开发人员能够立即访问新的移动操作系统特性和功能。开发人员不必等待Flutter团队公开新的移动操作系统功能。

### 我可以使用哪些操作系统来构建Flutter应用程序？

Flutter支持在Linux，Mac和Windows上开发。

### Flutter是以什么语言编写的？

我们查看了很多语言和运行时，最终采用了Dart作为框架和小部件。底层图形框架和Dart虚拟机以C/C++实现。

### Flutter为什么选择使用Dart？

Flutter使用四个主要维度进行评估，并考虑了框架作者，开发人员和最终用户的需求。我们发现某些语言符合某些要求，但Dart在所有评估维度上得分很高，并且符合我们的所有要求和标准。

Dart运行时和编译器支持Flutter的两个关键特性的组合：基于JIT的快速开发周期，允许在具有类型的语言中进行形状更改和状态热重载；以及提前编译器发出高效ARM代码，以快速启动和可预测的生产部署性能。

此外，我们还有机会与Dart社区密切合作，Dart社区积极投入资源改进Dart，以便在Flutter中使用。例如，当我们采用Dart时，该语言没有用于生成原生二进制文件的提前工具链，这有助于实现可预测的高性能；但现在有了，因为Dart团队为Flutter构建了它。同样，Dart VM之前已针对吞吐量进行了优化，但团队现在正在针对延迟优化VM，这对于Flutter的工作负载更为重要。

Dart在以下主要标准上得分很高：

* _开发人员生产力_。Flutter的主要价值主张之一是通过让开发人员使用相同的代码库为iOS和Android创建应用程序来节省工程资源。使用高效语言可以进一步加速开发人员，使Flutter更具吸引力。这对我们的框架团队和开发人员都非常重要。Flutter的大部分内容都是以我们提供给用户的相同语言构建的，因此我们需要在100k的代码行中保持高效，而不会牺牲框架和小部件对于开发人员的可接近性或可读性。

* _面向对象_。对于Flutter，我们需要一种适合Flutter问题域的语言：创建可视化用户体验。该行业在面向对象语言中构建用户界面框架已有数十年的经验。虽然我们可以使用非面向对象的语言，但这意味着重新发明轮子以解决几个难题。此外，绝大多数开发人员都具有面向对象开发的经验，因此可以更轻松地学习如何使用Flutter进行开发。

* _可预测，高性能_。通过Flutter，我们希望让开发人员能够创建快速，流畅的用户体验。为了实现这一点，我们需要能够在每个动画帧期间运行大量的最终开发人员代码。这意味着我们需要一种既能提供高性能又能提供可预测性能的语言，而不会产生导致帧丢失的周期性暂停。

* _快速分配_。Flutter框架使用功能样式的流，该流很大程度上依赖于底层内存分配器，有效地处理小的短期的分配。此样式是以具有此属性的语言开发的，并且在缺少此功能的语言中无法有效工作。

### Flutter可以运行任何Dart代码吗？

Flutter应该能够运行大多数不（传递或直接）导入dart:mirrors或dart:html的Dart代码。

### Flutter引擎有多大？

在2018年12月，我们测量了[最小Flutter应用程序]({{site.github}}/flutter/flutter/tree/75228a59dacc24f617272f7759677e242bbf74ec/examples/hello_world)
（没有Material组件，只有一个`Center`小部件，使用`flutter build apk`构建）捆绑并压缩为发行版APK的下载大小，大约为4.06MB。

对于这个简单的应用程序，核心引擎约为2.7MB（压缩），框架+应用程序代码约为820.6KB（压缩），LICENSE文件为53.5KB（压缩），必要的Java代码（classes.dex）为61.8KB （压缩），并且有大约450.4KB的（压缩的）ICU数据。

这些数据是使用内置于[Android Studio]({{site.android-dev}}/studio/build/apk-analyzer)中的[apkanalyzer]({{site.android-dev}}/studio/command-line/apkanalyzer)测量的。

根据Apple的App Store Connect报告，在iOS上，同一应用程序的发布IPA在iPhone X上的下载大小为10.8MB。IPA比APK大，主要是因为Apple加密了IPA中的二进制文件，使得压缩效率降低（请参阅Apple [QA1795](https://developer.apple.com/library/archive/qa/qa1795/_index.html)的[iOS App Store Specific
Considerations](https://developer.apple.com/library/archive/qa/qa1795/_index.html#//apple_ref/doc/uid/DTS40014195-CH1-APP_STORE_CONSIDERATIONS)部分）。

当然，情况因人而异，我们建议您测量自己的应用程序。要测量Android应用程序，请运行`flutter build apk`并将APK（`build/app/outputs/apk/release/app-release.apk`）加载到Android Studio（[说明]({{site.android-dev}}/studio/build/apk-analyzer)）中以获取详细的大小报告。要测量iOS应用程序，请将发布IPA上传到Apple的App Store Connect（[说明](/docs/deployment/ios)）并从那里获取大小报告。

## 功能

### 我可以期待什么样的应用程序性能？

你可以期待优异的性能。Flutter旨在帮助开发人员轻松实现60fps的恒定速度。Flutter应用程序通过本机编译的代码运行 - 不涉及解释器。这意味着Flutter应用程序可以快速启动。

### 我可以期待什么样的开发者周期？ 编辑和刷新之间有多长时间？ {#hot-reload}

Flutter实现了 _热重载_ 开发周期。您可以在设备或仿真器/模拟器上获得亚秒级重载时间。

Flutter的热重载是 _有状态的_，这意味着在重加载后保留应用状态。这意味着您可以在深度嵌套在应用程序中的屏幕上快速迭代，而无需在每次重加载后从主屏幕启动。

### “热重载”与“热重启”有什么不同？

热重载通过将更新的源代码文件注入正在运行的Dart VM（虚拟机）来工作。这不仅包括添加新类，还包括向现有类添加方法和字段，以及更改现有函数。但是，有些类型的代码更改无法进行热重载：

* 全局变量初始化器。
* 静态字段初始化器。
* 应用程序的`main()`方法。

有关其他详细信息，请参阅[使用热重载](/docs/development/tools/hot-reload)。

### 我可以在哪里部署Flutter应用程序？

您可以将Flutter应用程序编译并部署到iOS和Android。

### Flutter运行哪些设备和操作系统版本？

移动操作系统：Android Jelly Bean，v16,4.1.x或更新版本，以及iOS 8或更高版本。

移动硬件：iOS设备（iPhone 4S或更新版本）和ARM Android设备。

注意Flutter目前不支持为x86 Android直接构建（问题[#9253]({{site.github}}/flutter/flutter/issues/9253)），但在许多x86 Android设备上的为ARMv7或ARM64构建的应用程序运行良好（通过ARM仿真）。

我们支持使用Android和iOS设备以及Android仿真器和iOS模拟器开发Flutter应用程序。

我们在各种低端到高端手机上测试，但我们还没有正式的设备兼容性保证。

我们相信Flutter在平板电脑上运行良好。我们目前没有实施Material Design推荐的所有特定于平板电脑的改编，但我们正计划在该领域进一步投资。

### Flutter是否在Web上运行？

Flutter web目前正处于[技术预览阶段](https://flutter.dev/web)。我们正在Flutter存储库的分支中为Web开发Flutter。这样可以实现快速迭代，同时保持核心Flutter存储库稳定。您可以重新打包现有的Flutter代码以在Web预览上工作，但在我们仍处于预览状态时有一些警告。查看[说明](https://github.com/flutter/flutter-web)了解更多详情。

### 我可以使用Flutter构建桌面应用程序吗？

是的，但是现在它得不到很好的支持。我们正在努力使这成为一流的体验。我们目前的进展记录在[我们的维基](https://github.com/flutter/flutter/wiki/Desktop-shells)上。

### 我可以在现有的原生应用程序中使用Flutter吗？

是的，您可以在现有的Android或iOS应用程序中嵌入Flutter视图，但是我们的工具目前尚未针对此用例进行全面优化（有关详细信息，请参阅问题[#14821]({{site.github}}/flutter/flutter/issues/14821)）。

目前的两个演示是[platform_view]({{site.github}}/flutter/flutter/tree/master/examples/platform_view)
和[flutter_view]({{site.github}}/flutter/flutter/tree/master/examples/flutter_view)示例。
维基页面[将Flutter添加到现有应用程序]({{site.github}}/flutter/flutter/wiki/Add-Flutter-to-existing-apps)中提供了一些初始文档。

### 我可以访问传感器和本地存储等平台服务和API吗？

是的。Flutter为开发人员提供了对操作系统中某些特定于平台的服务和API的开箱即用访问。但是，我们希望避免大多数跨平台API的“最小公分母”问题，因此我们不打算为所有本机服务和API构建跨平台API。

许多平台服务和API都在Pub站点中提供[现成的包]({{site.pub}}/flutter/)。[使用现有的包](/docs/development/packages-and-plugins/using-packages)很容易。

最后，我们鼓励开发人员使用Flutter的异步消息传递系统来创建自己与[平台和第三方API](/docs/development/platform-integration/platform-channels)的集成。开发人员可以根据需要公开尽可能多或少的平台API，并构建最适合其项目的抽象层。

### 我可以扩展和自定义捆绑的小部件吗？

绝对可以。Flutter的小部件系统旨在轻松定制。

Flutter不是让每个小部件都提供大量参数，而是包含组合。小部件是由较小的小部件构建的，您可以重用它们并以新颖的方式组合以制作自定义小部件。例如，RaisedButton不是子类化通用按钮小部件，而是将Material小部件与GestureDetector小部件组合在一起。Material小部件提供可视化设计，GestureDetector小部件提供交互设计。

要创建具有自定义可视设计的按钮，您可以将实现可视化设计的小部件与提供交互设计的GestureDetector结合使用。例如，CupertinoButton遵循这种方法，并将GestureDetector与其他几个实现其可视化设计的小部件组合在一起。

组合使您可以最大限度地控制小部件的可视化和交互设计，同时还允许大量代码重用。在框架中，我们将复杂的小部件分解为分别实现视觉，交互和动作设计的部分。您可以重新混合这些小部件，但是您希望制作具有完整表达范围的自定义小部件。

### 为什么我要在iOS和Android之间共享布局代码？

您可以选择为iOS和Android实现不同的应用布局。开发人员可以在运行时自由检查移动操作系统并呈现不同的布局，但我们发现这种做法很少见。

越来越多地，我们看到移动应用程序的布局和设计在各个平台上都在不断发展，变得更加品牌驱动和统一。这意味着在iOS和Android上共享布局和UI代码的强烈动机。

应用程序美学设计的品牌识别和定制现在变得比严格遵循传统平台美学更重要。例如，应用程序设计通常需要自定义字体、颜色、形状、动作等，以便清楚地传达其品牌标识。

我们还看到在iOS和Android上部署的常见布局模式。例如，现在可以在iOS和Android上自然找到“底部导航栏”模式。移动平台上的设计理念似乎趋于一致。

### 我可以与移动平台的默认编程语言互操作吗？

是的，Flutter支持调用平台，包括在Android上集成Java或Kotlin代码，在iOS上集成ObjectiveC或Swift代码。这是通过灵活的消息传递样式启用的，其中Flutter应用可以使用[`BasicMessageChannel`]({{site.api}}/flutter/services/BasicMessageChannel-class.html)向移动平台发送和接收消息。

了解有关使用[平台渠道](/docs/development/platform-integration/platform-channels)访问Flutter中的平台和第三方服务的更多信息。

[这里]({{site.github}}/flutter/flutter/tree/master/examples/platform_channel)有一个示例项目，演示如何使用平台通道访问iOS和Android上的电池状态信息。

### Flutter是否带有反射/镜像系统？

目前还没有。由于Flutter应用程序是预编译用于生产，并且二进制大小始终是移动应用程序的一个问题，因此我们禁用了dart:mirrors。 我们很想知道您可能需要反射/镜像&mdash;请通过[{{site.email}}](mailto:{{site.email}})告诉我们。

### 如何在Flutter中进行国际化（i18n），本地化（l10n）和可访问性（a11y）？

在[国际化教程](/docs/development/accessibility-and-localization/internationalization)中了解有关i18n和l10n的更多信息。

在[可访问性文档](/docs/development/accessibility-and-localization/accessibility)中了解有关a11y的更多信息。

### 如何为Flutter编写并行和/或并发应用程序？

Flutter支持隔离。隔离是Flutter VM中的独立堆，它们能够并行运行（通常作为单独的线程实现）。隔离通过发送和接收异步消息进行通信。Flutter目前没有共享内存并行解决方案，尽管我们正在为此评估解决方案。

查看[使用Flutter隔离的示例]({{site.github}}/flutter/flutter/blob/master/examples/layers/services/isolate.dart)。

### 我可以在Flutter应用程序的后台运行Dart代码吗？

是的，您可以在iOS和Android上的后台进程中运行Dart代码。有关更多信息，请参阅Medium文章[使用Flutter插件和Geofencing在后台中执行Dart]({{site.flutter-medium}}/executing-dart-in-the-background-with-flutter-plugins-and-geofencing-2b3e40a1a124)。

### 我可以在Flutter中使用JSON/XML/<wbr>protobuffers等吗？

绝对可以。[Pub网站]({{site.pub}})上有用于JSON，XML，protobufs以及许多其他实用程序和格式的库。

有关在Flutter中使用JSON的详细说明，请查看[JSON教程](/docs/development/data-and-backend/json)。

### 我可以使用Flutter构建3D（OpenGL）应用程序吗？

今天我们不支持通过OpenGL ES或类似软件实现3D。我们有长期计划来公开优化的3D API，但现在我们专注于2D。

### 为什么我的APK或IPA如此之大？

通常，包括图像、声音文件、字体等在内的资产是APK或IPA的主要部分。Android和iOS生态系统中的各种工具可以帮助您了解APK或IPA中的内容。

此外，请务必使用Flutter工具创建APK或IPA的 _发布版本_。发布版本通常比 _调试版本_ 小得多。

详细了解如何创建[Android应用的发布版本](/docs/deployment/android)，以及创建[iOS应用的发布版本](/docs/deployment/ios)。

### Flutter应用程序是否在Chromebook上运行？

我们已经看到Flutter应用在某些Chromebook上运行。我们正在跟踪[与在Chromebook上运行Flutter相关的问题]({{site.github}}/flutter/flutter/labels/platform-arc)。

## 框架

### 为什么build()方法在State上，而不是StatefulWidget上？

在State上放置`Widget build(BuildContext context)`方法，而不是在StatefulWidget上放置`Widget build(BuildContext context, State state)`方法，可以在子类化StatefulWidget时为开发人员提供更大的灵活性。您可以阅读更多[API文档上State.build的详细讨论]({{site.api}}/flutter/widgets/State/build.html)。

### Flutter的标记语言在哪里？为什么Flutter没有标记语法？

Flutter UI使用命令式，面向对象的语言构建（Dart，用于构建Flutter框架的相同语言）。Flutter不附带声明性标记。

我们发现使用代码动态构建的UI允许更大的灵活性。例如，我们发现严格的标记系统难以表达和生成具有定制行为的自定义小部件。

我们还发现，我们的“代码优先”更好地允许热重载和动态环境适应等功能。

可以创建自定义语言，然后即时转换为小部件。因为构建方法只是“代码”，所以它们可以做任何事情，包括解释标记并将其转换为小部件。

### 我的应用程序右上角有一个Debug横幅/功能区。我为什么看到这个？

默认情况下，`flutter run`命令使用调试构建配置。

调试配置在VM（虚拟机）中运行Dart代码，从而实现[热重载](#hot-reload)的快速开发周期（发布构建使用标准的[Android](#run-android)和[iOS](#run-ios)工具链进行编译）。

调试配置还会检查所有断言，这有助于您在开发过程中尽早捕获错误，但会产生运行时成本。“Debug”横幅表示已启用这些检查。您可以在没有这些检查的情况下运行您的应用程序，方法是使用`flutter run`的`--profile`或`--release`标志。

如果您使用的是IntelliJ的Flutter插件，则可以使用菜单条目**Run > Flutter Run in Profile Mode**或**Release Mode**在配置文件或发布模式下启动应用程序。

### Flutter的框架使用什么编程范式？

Flutter是一个多范式的编程环境。在过去几十年中开发的许多编程技术都在Flutter中使用。我们使用每一个我们相信该技术的优势使其特别适合。没有特别的顺序：

* 组合：Flutter使用的主要范例是使用具有窄范围行为的小对象，组合在一起以获得更复杂的效果。Flutter小部件库中的大多数小部件都是以这种方式构建的。例如，Material [FlatButton]({{site.api}}/flutter/material/FlatButton-class.html)类是使用[MaterialButton]({{site.api}}/flutter/material/MaterialButton-class.html)类构建的，该类本身是使用[IconTheme]({{site.api}}/flutter/widgets/IconTheme-class.html)、[InkWell]({{site.api}}/flutter/material/InkWell-class.html)、[Padding]({{site.api}}/flutter/widgets/Padding-class.html)、[Center]({{site.api}}/flutter/widgets/Center-class.html)、[Material]({{site.api}}/flutter/material/Material-class.html)、[AnimatedDefaultTextStyle]({{site.api}}/flutter/widgets/AnimatedDefaultTextStyle-class.html)和[ConstrainedBox]({{site.api}}/flutter/widgets/ConstrainedBox-class.html)构建的。[InkWell]({{site.api}}/flutter/material/InkWell-class.html)使用[GestureDetector]({{site.api}}/flutter/widgets/GestureDetector-class.html)构建。[Material]({{site.api}}/flutter/material/Material-class.html)使用[AnimatedDefaultTextStyle]({{site.api}}/flutter/widgets/AnimatedDefaultTextStyle-class.html)，[NotificationListener]({{site.api}}/flutter/widgets/NotificationListener-class.html)和[AnimatedPhysicalModel]({{site.api}}/flutter/widgets/AnimatedPhysicalModel-class.html)构建。等等。它的小部件都按照这种方式一直向下。

* 函数式编程：整个应用程序可以只使用[StatelessWidget]({{site.api}}/flutter/widgets/StatelessWidget-class.html)构建，它本质上是描述参数如何映射到其他函数的函数，在计算布局或绘制图形的原语中自下而上。（此类应用程序不能轻易拥有状态，因此通常是非交互式的。）例如，[Icon]({{site.api}}/flutter/widgets/Icon-class.html)小部件本质上是一个将其参数（[color]({{site.api}}/flutter/widgets/Icon/color.html)，[icon]({{site.api}}/flutter/widgets/Icon/icon.html)，[size]({{site.api}}/flutter/widgets/Icon/size.html)）映射到布局原语的函数。此外，大量使用不可变数据结构，包括整个[Widget]({{site.api}}/flutter/widgets/Widget-class.html)类层次结构以及许多支持类，如[Rect]({{site.api}}/flutter/dart-ui/Rect-class.html)和[TextStyle]({{site.api}}/flutter/painting/TextStyle-class.html)。在较小的范围内，Dart的[Iterable]({{site.api}}/flutter/dart-core/Iterable-class.html) API（大量使用函数样式（map，reduce，where等））经常用于处理框架中的值列表。

* 事件驱动的编程：用户交互由调度到事件处理程序注册的回调的事件对象表示。屏幕更新由类似的回调机制触发。[Listenable]({{site.api}}/flutter/foundation/Listenable-class.html)类用作动画系统的基础，它为具有多个监听器的事件规范了订阅模型。

* 基于类的面向对象编程：框架的大多数API都是使用具有继承的类构建的。我们使用一种方法，在我们的基类中定义非常高级的API，然后在子类中迭代地对它们进行专门化。例如，我们的渲染对象有一个与坐标系无关的基类（[RenderObject]({{site.api}}/flutter/rendering/RenderObject-class.html)），然后我们有一个引入了几何应该基于笛卡尔坐标系（x/宽度和Y/高度）的观点的子类（[RenderBox]({{site.api}}/flutter/rendering/RenderBox-class.html)）。

* 基于原型的面向对象编程：[ScrollPhysics]({{site.api}}/flutter/widgets/ScrollPhysics-class.html)类链接实例以组成应用于在运行时动态滚动的物理。这使得系统可以构建具有平台特定物理的分页物理，而无需在编译时选择平台。

* 命令式编程：直接命令式编程，通常与封装在对象中的状态配对，用于提供最直观的解决方案。例如，测试以命令式样式编写，首先描述测试中的情况，然后列出测试必须匹配的不变量，然后推进时钟或插入测试所需的事件。

* 反应式编程：小部件和元素树有时被描述为反应式的，因为小部件构造函数中提供的新输入会立即传播为小部件构建方法对较低级别小部件的更改，以及较低小部件中所做的更改（例如，响应用户输入）通过事件处理程序传播回树。功能反应和命令反应的方面都存在于框架中，具体取决于小部件的需求。具有构建方法的小部件（仅由描述小部件如何对其配置中的更改作出反应的表达式组成）是函数式性反应性小部件（例如，Material [Divider]({{site.api}}/flutter/material/Divider-class.html)类）。其构建方法在多个语句上构造子小部件列表的小部件（描述小部件对其配置更改的反应）是命令式反应性小部件（例如[Chip]({{site.api}}/flutter/material/Chip-class.html)类）。

* 声明性编程：小部件的构建方法通常是具有多级嵌套构造函数的单个表达式，使用严格声明的Dart子集编写。这种嵌套表达式可以机械地转换为任何适当表达的标记语言或从任何适当表达的标记语言转换。例如，[UserAccountsDrawerHeader]({{site.api}}/flutter/material/UserAccountsDrawerHeader-class.html)小部件具有长构建方法（20多行），由单个嵌套表达式组成。 这也可以与命令式风格相结合，以构建在纯粹声明性方法中难以描述的UI。

* 泛型编程：类型可用于帮助开发人员尽早发现编程错误。Flutter框架使用泛型编程来帮助实现这一目标。例如，[State]({{site.api}}/flutter/widgets/State-class.html)类根据其关联小部件的类型进行参数化，以便Dart分析器可以捕获状态和小部件的不匹配。类似地，[GlobalKey]({{site.api}}/flutter/widgets/GlobalKey-class.html)类接受一个类型参数，以便它可以以类型安全的方式（使用运行时检查）访问远程小部件的状态，[Route]({{site.api}}/flutter/widgets/Route-class.html)接口使用[弹出]({{site.api}}/flutter/widgets/Navigator/pop.html)时预期使用的类型进行参数化，而像[List]({{site.api}}/flutter/dart-core/List-class.html)、[Map]({{site.api}}/flutter/dart-core/Map-class.html)和[Set]({{site.api}}/flutter/dart-core/Set-class.html)这样的集合都是参数化的，因此可以在分析期间或在调试期间的运行时提前捕获不匹配的元素。

* 并发编程：Flutter大量使用[Future]({{site.api}}/flutter/dart-async/Future-class.html)和其他异步API。例如，动画系统通过完成future来报告动画何时结束。图像加载系统类似地使用future来报告加载完成的时间。

* 约束编程：Flutter中的布局系统使用弱形式的约束编程来确定场景的几何形状。约束（例如，对于笛卡尔盒子，最小和最大宽度以及最小和最大高度）从父传递给子，并且子选择结果几何形状（例如，对于笛卡尔盒子，尺寸，特别是宽度和高度））满足这些限制。通过使用这种技术，Flutter通常可以通过一次通过布局整个场景。

## 项目

### 我可以在哪里获得支持？

如果您认为自己遇到了错误，请在我们的[问题跟踪器]({{site.github}}/flutter/flutter/issues)中提交。我们鼓励您使用[Stack Overflow]({{site.so}}/tags/flutter)进行“HOWTO”类型的问题。如需讨论，请加入我们的邮件列表[{{site.email}}](mailto:{{site.email}})。

### 我如何参与？

Flutter是开源的，我们鼓励您做出贡献。您可以先在我们的[问题跟踪器]({{site.github}}/flutter/flutter/issues)中为功能请求和错误提交问题。

我们建议您加入我们的邮件列表[{{site.email}}](mailto:{{site.email}})，告诉我们您如何使用Flutter以及您希望使用它做什么。

如果您对贡献代码感兴趣，可以从阅读我们的[贡献指南]({{site.github}}/flutter/flutter/blob/master/CONTRIBUTING.md)开始，并查看我们的[简单入门问题]({{site.github}}/flutter/flutter/issues?q=is%3Aopen+is%3Aissue+label%3A%22easy+fix%22)列表。

### Flutter是否开源？

是的，Flutter是开源技术。你可以在[GitHub]({{site.github}}/flutter/flutter)上找到这个项目。

### 哪些软件许可证适用于Flutter及其依赖项？

Flutter包括两个组件：作为动态链接二进制文件发布的引擎，以及作为引擎加载的单独二进制文件的Dart框架。引擎使用多个具有许多依赖项的软件组件；查看其[许可证文件](https://raw.githubusercontent.com/flutter/engine/master/sky/packages/sky_engine/LICENSE)中的完整列表。

该框架完全是独立的，只需要一个[许可证]({{site.github}}/flutter/flutter/blob/master/LICENSE)。

此外，您使用的任何Dart包都可能有自己的许可证要求。

### 如何确定Flutter应用程序需要显示的许可证？

有一个API可以找到您需要显示的许可证列表：

* 如果您的应用程序有[Drawer]({{site.api}}/flutter/material/Drawer-class.html)，请添加[AboutListTile]({{site.api}}/flutter/material/AboutListTile-class.html)。

* 如果您的应用程序无Drawer但是使用了Material组件库，请调用[showAboutDialog]({{site.api}}/flutter/material/showAboutDialog.html)或[showLicensePage]({{site.api}}/flutter/material/showLicensePage.html)。

* 对于更自定义的方法，您可以从[LicenseRegistry]({{site.api}}/flutter/foundation/LicenseRegistry-class.html)获取原始许可证。

### 谁为Flutter工作？

Flutter是一个开源项目。目前，大部分开发工作都是由Google的工程师完成的。如果您对Flutter感到兴奋，我们鼓励您加入社区并为Flutter做出贡献！

[widgets]: /docs/development/ui/widgets

### Flutter的指导原则是什么？

我们相信：

* 为了覆盖每个潜在用户，开发人员需要针对多个移动平台。
* 由于自动行为（滚动，布局）和传统支持，当今存在的HTML和WebView使得始终如一地达到高帧率并提供高保真体验具有挑战性。
* 今天，多次构建同一个应用程序的成本太高：它需要不同的团队，不同的代码库，不同的工作流程，不同的工具等。
* 开发人员想要一种更简单，更好的方法来使用单个代码库为多个目标平台构建移动应用程序，并且他们不想牺牲质量、控制或性能。

我们专注于三件事：

* _控制_ - 开发人员应该访问和控制系统的所有层。这导致：
* _性能_ - 用户应该得到完美流畅，响应迅速，无应力的应用程序。这导致：
* _逼真_ - 每个人都应该获得精准，美观，愉悦的移动应用体验。

### Apple会拒绝我的Flutter应用吗？

我们不能代表Apple，但Apple的政策多年来一直在变化，他们的App Store包含许多使用Unity和Flutter等技术构建的应用程序。Apple甚至推出了像[Hamilton][Hamilton for iOS]这样的Flutter应用程序。
Apple has even featured Flutter apps such as [Hamilton.][Hamilton for iOS]

当然，Apple最终负责他们的生态系统，但我们的目标是继续尽我们所能确保将Flutter应用程序部署到Apple的App Store。

[Hamilton for Android]: https://play.google.com/store/apps/details?id=com.hamilton.app
[Hamilton for iOS]: https://itunes.apple.com/us/app/hamilton-the-official-app/id1255231054?mt=8
