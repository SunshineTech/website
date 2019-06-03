---
title: 技术概述
---

## Flutter是什么？

Flutter是一个移动应用SDK，可通过单一代码库为iOS和Android构建高性能，高保真的应用。

目标是使开发人员能够提供在不同平台上感觉自然的高性能应用程序。 我们接受滚动行为，排版，图标等方面的差异。

<object type="image/svg+xml" data="/images/whatisflutter/hero-shrine.svg" style="width: 100%; height: 100%;"></object>

这是[Gallery]({{site.github}}/flutter/flutter/tree/master/examples/flutter_gallery/lib/demo)中的演示应用程序，这是一组Flutter示例应用程序，您可以在安装Flutter并设置环境后运行。Shrine具有高质量的滚动图像，交互式卡片，按钮，下拉列表和购物车页面。 要查看此单个代码库以及更多示例，请[访问我们的GitHub存储库]({{site.github}}/flutter/flutter/tree/master/examples)。

入门无需移动开发经验。应用程序是用[Dart]({{site.dart-site}})编写的，如果您使用的是Java或JavaScript等语言，它看起来很熟悉。使用面向对象语言的经验肯定是有帮助的，但即使是非程序员也制作了Flutter应用程序！

## 为什么使用Flutter？

Flutter有哪些优点？它可以帮助你：

*   高效率
    *   从单一代码库开发iOS和Android
    *   使用更少的代码，甚至在单个操作系统上，使用现代，富有表现力的语言和声明性方法做更多事情
    *   原型并轻松迭代
        *   通过在应用运行时（使用热重载）更改代码和重载进行实验
        *   修复崩溃并从应用程序停止的位置继续调试
*   创建美观，高度定制的用户体验
    *   受益于丰富的Material Design和使用Flutter自己的框架构建的Cupertino（iOS风格）小部件
    *   实现定制、美观、品牌驱动的设计，不受OEM小部件集的限制

## 核心原则

Flutter包括现代反应式框架，2D渲染引擎，现成的小部件和开发工具。这些组件协同工作，帮助您设计、构建、测试和调试应用程序。一切都围绕一些核心原则组织。

### 一切都是小部件

小部件是Flutter应用程序用户界面的基本构建块。每个小部件都是用户界面的一部分的不可变声明。与分隔视图、视图控制器、布局和其他属性的其他框架不同，Flutter具有一致的统一对象模型：小部件。

小部件可以定义：

*   结构元素（如按钮或菜单）
*   风格元素（如字体或颜色方案）
*   布局的一个方面（如填充）
*   等等...

小部件基于组合形成层次结构。每个小部件都嵌套在其内部，并从其父级继承属性。没有单独的“应用程序”对象。相反，根小部件服务于此角色。

您可以通过告诉框架将层次结构中的小部件替换为另一个小部件来响应事件，例如用户交互。然后，框架比较新旧小部件并有效地更新用户界面。

#### 组合 > 继承

小部件本身通常由许多小的，单一用途的小部件组成，这些小部件组合起来产生强大的效果。
例如，[Container]({{site.github}}/flutter/flutter/blob/master/packages/flutter/lib/src/widgets/container.dart)是一个常用的小部件，由几个负责布局、绘制、定位和大小调整的小部件组成。 具体来说，Container由
[LimitedBox]({{site.api}}/flutter/widgets/LimitedBox-class.html)，
[ConstrainedBox]({{site.api}}/flutter/widgets/ConstrainedBox-class.html)，
[Align]({{site.api}}/flutter/widgets/Align-class.html)，
[Padding]({{site.api}}/flutter/widgets/Padding-class.html)，
[DecoratedBox]({{site.api}}/flutter/widgets/DecoratedBox-class.html)
和[Transform]({{site.api}}/flutter/widgets/Transform-class.html)
小部件组成。您可以用新颖的方式组合这些以及其他简单的小部件，而不是将Container子类化以生成自定义效果。

类层次结构浅而宽，以最大化可能的组合数。

<object type="image/svg+xml" data="/images/whatisflutter/diagram-widgetclass.svg" style="width: 100%; height: 100%;"></object>

您还可以通过将小部件与其他小部件组合来控制小部件的*布局*。例如，要将小部件居中，请将其包装在Center小部件中。有填充，对齐，行，列和网格的小部件。这些布局小部件没有自己的可视化表示。相反，他们唯一的目的是控制另一个小部件布局的某些方面。要了解小部件以某种方式呈现的原因，检查相邻小部件通常很有帮助。

#### 分层蛋糕很美分

Flutter框架被组织成一系列层，每层构建在前一层上。

<object type="image/svg+xml" data="/images/whatisflutter/diagram-layercake.svg" style="width: 85%; height: 85%"></object>

框架的上层比下层更频繁地使用。有关构成Flutter分层框架的完整库集，请参阅我们的[API文档]({{site.api}})。

此设计的目标是帮助您使用更少的代码完成更多工作。例如，Material层是通过从小部件层组合基本小部件构建的，小部件层本身是通过编译渲染层中的低级对象来构建的。

这些层提供了许多构建应用程序的选项。选择一种自定义方法来释放框架的全部表现力，或者使用小部件层中的构建块，或混合搭配。您可以组合Flutter提供的现成小部件，或使用Flutter团队用于构建框架的相同工具和技术创建您自己的自定义小部件。

没有什么是对你隐藏的。您可以从高级别、统一的小部件概念中获得生产力优势，而不必牺牲深入到较低层的能力。

### 构建小部件

您可以通过实现返回小部件的树（或层次结构）的[build]({{site.api}}/flutter/widgets/StatelessWidget/build.html)
函数来定义小部件的独特特征。此树以更具体的术语表示小部件的用户界面部分。例如，工具栏小部件可能具有构建函数，该函数返回某些
[文本]({{site.api}}/flutter/widgets/Text-class.html)和[各种]({{site.api}}/flutter/material/IconButton-class.html)
[按钮]({{site.api}}/flutter/material/PopupMenuButton-class.html)的
[水平布局]({{site.api}}/flutter/widgets/Row-class.html)。
然后框架递归地要求构建这些小部件中的每一个，直到该过程在[完全具体的小部件]({{site.api}}/flutter/widgets/RenderObjectWidget-class.html)中达到最低点，然后框架将这些小部件拼接成树。

小部件的构建函数应该没有副作用。无论何时要求构建，小部件都应返回一个新的小部件树，无论小部件先前返回了什么。该框架大大提升了将先前构建与当前构建进行比较并确定需要对用户界面进行哪些修改。

这种自动比较非常有效，可实现高性能的交互式应用。构建函数的设计通过专注于声明构成小部件的内容，而不是将用户界面从一个状态更新到另一个状态的复杂性，来简化代码。

### 处理用户交互

如果小部件的独特特征需要根据用户交互或其他因素进行更改，则该小部件是有状态的。例如，如果小部件具有每当用户点击按钮时递增的计数器，则计数器的值是该小部件的状态。当该值更改时，需要重建窗口小部件以更新UI。

这些小部件是[StatefulWidget]({{site.api}}/flutter/widgets/StatefulWidget-class.html)
（而不是[StatelessWidget]({{site.api}}/flutter/widgets/StatelessWidget-class.html)
）的子类，并将其可变状态存储在[State]({{site.api}}/flutter/widgets/State-class.html)的子类中。

<object type="image/svg+xml" data="/images/whatisflutter/diagram-state.svg" style="width: 85%; height: 85%"></object>

无论何时改变State对象（例如，递增计数器），都必须调用[setState]({{site.api}}/flutter/widgets/State/setState.html)()
以通过再次调用State的构建方法来通知框架更新用户界面。有关管理状态的示例，请参阅使用每个新Flutter项目创建的
[MyApp模板]({{site.github}}/flutter/flutter/blob/master/packages/flutter_tools/templates/app/lib/main.dart.tmpl)。

具有单独的状态和小部件对象允许其他小部件以相同的方式处理无状态和有状态小部件，而不用担心丢失状态。父小部件可以自由地创建子小部件的新实例而不会丢失子小部件的持久状态，而不需要保持子小部件以保持其状态。 该框架在适当时执行查找和重用现有状态对象的所有工作。

## 试试看！

现在您已熟悉Flutter框架的基本结构和原理，以及如何构建应用程序并使它们具有交互性，您已准备好开始开发和迭代。

接下来的步骤：

1.  按照[Flutter入门指南](/docs/get-started)进行操作。
1.  尝试[构建布局教程](/docs/development/ui/layout/tutorial)和[为您的Flutter应用程序添加交互性](/docs/development/ui/interactive)。
1.  按照[小部件框架之旅](/docs/development/ui/widgets-intro)中的详细示例进行操作。

## 获取支持

跟踪Flutter项目并以各种方式加入对话。我们是开源的，很乐意听取您的意见。

- [提问可以通过特定解决方案回答的HOWTO问题][so]
- [与Flutter工程师和用户实时聊天][gitter]
- [在我们的邮件列表上讨论Flutter，最佳实践，应用程序设计等][mailinglist]
- [报告错误，请求功能和文档][issues]
- [在Twitter上关注我们：@flutterdev](https://twitter.com/flutterdev/)


[issues]: {{site.github}}/flutter/flutter/issues
[apidocs]: {{site.api}}
[so]: {{site.so}}/tags/flutter
[mailinglist]: {{site.groups}}/d/forum/flutter-dev
[gitter]: https://gitter.im/flutter/flutter
