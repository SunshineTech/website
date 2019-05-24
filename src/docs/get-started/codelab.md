---
title: 编写您的第一个Flutter应用程序（第1部分）
short-title: 编写您的第一个应用程序
prev:
  title: 试驾
  path: /docs/get-started/test-drive
next:
  title: 了解更多
  path: /docs/get-started/learn-more
diff2html: true
---

{% assign code-url = 'https://raw.githubusercontent.com/flutter/codelabs/master' -%}

{% asset get-started/startup-namer-part-1 alt="The app that you'll be building" class='site-image-right' %}

{%- comment %}
  Code highlights in this page are green, to match diff additions.
{% endcomment -%}
<style>pre .highlight { background-color: #dfd; }</style>

这是创建第一个Flutter应用程序的指南。如果您熟悉面向对象的代码和基本编程概念（如变量，循环和条件），则可以完成本教程。您不需要以前使用Dart或移动编程的经验。

本指南是两部分代码实验室的第1部分。您可以在[Google Developers]({{site.codelabs}})上找到[第2部分]({{site.codelabs}}/codelabs/first-flutter-app-pt2)。[第1部分]({{site.codelabs}}/codelabs/first-flutter-app-pt1)也可以在[Google Developers]({{site.codelabs}})上找到。

## 您将在第1部分中构建的内容
{:.no_toc}

您将实现一个简单的移动应用程序，为初创公司生成建议的名称。用户可以选择和取消选择名称，保存最佳名称。代码延迟生成名称。当用户滚动时，会生成更多名称。用户可以滚动的距离没有限制。

动画GIF显示应用程序在第1部分完成时的工作方式。

{{site.alert.secondary}}
  <h4 class="no_toc">您将在第1部分学到什么</h4>

  * 如何编写在iOS和Android上看起来很自然的Flutter应用程序。
  * Flutter应用程序的基本结构。
  * 查找和使用包来扩展功能。
  * 使用热重载更快开发周期。
  * 如何实现有状态小部件。
  * 如何创建一个无限的，延迟加载的列表。

  在此代码实验室的[第2部分]({{site.codelabs}}/codelabs/first-flutter-app-pt2)中，您将添加交互性，修改应用程序的主题，并添加导航到新屏幕的功能（在Flutter中称为 _路由_）。
{{site.alert.end}}

{{site.alert.secondary}}
  <h4 class="no_toc">您将使用什么</h4>

  您需要两个软件才能完成本实验：[Flutter SDK](/docs/get-started/install)和[编辑器](/docs/get-started/editor)。此代码实验室采用Android Studio，但您可以使用首选编辑器。

  您可以使用以下任何设备运行此代码实验室：

  * 连接到计算机并设置为开发人员模式的物理设备（[Android](install/macos#set-up-your-android-device)或[iOS](install/macos#deploy-to-ios-devices)）。
  * [iOS模拟器](install/macos#set-up-the-ios-simulator)。
  * [Android模拟器](install/macos#set-up-the-android-emulator)。
{{site.alert.end}}

## 第1步：创建启动器Flutter应用程序

<?code-excerpt path-base="codelabs/startup_namer/step1_base"?>

使用[开始第一个Flutter应用程序](/docs/get-started/test-drive#create-app)中的说明创建一个简单的模板化Flutter应用程序。将项目命名为**startup_namer**（而不是 _myapp_）。

{{site.alert.tip}}
  如果您没有在IDE中看到“New Flutter Project”选项，请确保[已为Flutter和Dart安装了插件](/docs/get-started/editor)。
{{site.alert.end}}

在这个代码实验室中，你将主要编辑Dart代码所在位置的**lib/main.dart**。

 1. 替换`lib/main.dart`的内容。<br>
    删除**lib/main.dart**中的所有代码。替换为以下代码，在屏幕中央显示“Hello World”。

    <?code-excerpt "lib/main.dart" title?>
    ```dart
    import 'package:flutter/material.dart';

    void main() => runApp(MyApp());

    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          title: 'Welcome to Flutter',
          home: Scaffold(
            appBar: AppBar(
              title: Text('Welcome to Flutter'),
            ),
            body: Center(
              child: Text('Hello World'),
            ),
          ),
        );
      }
    }
    ```

    {{site.alert.tip}}
      将代码粘贴到应用程序中时，缩进可能会出现偏差。您可以使用Flutter工具自动修复此问题：

      * Android Studio / IntelliJ IDEA：右键单击代码，然后选择**使用dartfmt重新格式化代码**。
      * VS Code：右键单击并选择**格式化文档**。
      * 终端：运行`flutter format <filename>`。
    {{site.alert.end}}

 2. [按照IDE描述的方式](/docs/get-started/test-drive)运行应用程序。您应该看到Android或iOS输出，这具体取决于您的设备。

    {% indent %}
      {% include android-ios-figure-pair.md image="hello-world.png" alt="Hello world app" %}
    {% endindent %}

    {{site.alert.tip}}
      第一次在物理设备上运行时，可能需要一段时间加载。在此之后，您可以使用热重载快速更新。如果应用程序正在运行，**保存**也会执行热重载。
    {{site.alert.end}}

### 观察
{:.no_toc}

* 此示例创建一个Material应用程序。[Material]({{site.material}}/guidelines)是一种视觉设计语言，是移动和Web上的标准。Flutter提供了丰富的Material小部件。
* `main()`方法使用箭头（`=>`）表示法。对单行函数或方法使用箭头表示法。
* 该应用程序扩展了`StatelessWidget`，使应用程序本身成为一个小部件。在Flutter中，几乎所有东西都是一个小部件，包括对齐、填充和布局。
* Material库中的`Scaffold`小部件提供默认的应用程序栏，标题和包含主屏幕小部件树的主体属性。小部件子树可能非常复杂。
* 小部件的主要工作是提供`build()`方法，该方法描述如何根据其他较低级别的小部件显示小部件。
* 此示例的主体包含一个包含`Text`子小部件的`Center`小部件。Center小部件将其小部件子树与屏幕中心对齐。

## 第2步：使用外部包

在这一步中，您将开始使用名为[english_words]({{site.pub}}/packages/english_words)的开源包，其中包含几千个最常用的英语单词和一些实用程序函数。

您可以在[Pub网站]({{site.pub}}/flutter)上找到`english_words`包以及许多其他开源包。

 1. pubspec文件管理Flutter应用程序的资产和依赖项。在`pubspec.yaml`中，将`english_words`（3.1.0或更高版本）添加到依赖项列表：

    <?code-excerpt path-base="codelabs/startup_namer"?>
    <?code-excerpt "{step1_base,step2_use_package}/pubspec.yaml" diff-u="4" from="dependencies" to="english"?>
    ```diff
    --- step1_base/pubspec.yaml
    +++ step2_use_package/pubspec.yaml
    @@ -5,4 +5,5 @@
     dependencies:
       flutter:
         sdk: flutter
       cupertino_icons: ^0.1.2
    +  english_words: ^3.1.0
    ```

 2. 在Android Studio的编辑器视图中查看pubspec时，单击**Packages get**。这会将包拉入您的项目中。您应该在控制台中看到以下内容：

    ```terminal
    $ flutter packages get
    Running "flutter packages get" in startup_namer...
    Process finished with exit code 0
    ```

    执行`Packages get`也会自动生成`pubspec.lock`文件，其中包含项目中所有包的列表及其版本号。

 3. 在`lib/main.dart`中，导入新包：

    <?code-excerpt path-base="codelabs/startup_namer/step2_use_package"?>
    <?code-excerpt "lib/main.dart" title retain="/^import/" replace="/import.*?english.*/[!$&!]/g" indent-by="2"?>
    ```dart
      import 'package:flutter/material.dart';
      [!import 'package:english_words/english_words.dart';!]
    ```

    在您键入时，Android Studio会为您提供导入库的建议。然后它将导入字符串呈现为灰色，让您知道导入的库未使用（到目前为止）。

 4. 使用英语单词包生成文本而不是使用字符串“Hello World”：

    <?code-excerpt path-base="codelabs/startup_namer"?>
    <?code-excerpt "{step1_base,step2_use_package}/lib/main.dart" from="class"?>
    ```diff
    --- step1_base/lib/main.dart
    +++ step2_use_package/lib/main.dart
    @@ -5,6 +6,7 @@
     class MyApp extends StatelessWidget {
       @override
       Widget build(BuildContext context) {
    +    final wordPair = WordPair.random();
         return MaterialApp(
           title: 'Welcome to Flutter',
           home: Scaffold(
    @@ -12,7 +14,7 @@
               title: Text('Welcome to Flutter'),
             ),
             body: Center(
    -          child: Text('Hello World'),
    +          child: Text(wordPair.asPascalCase),
             ),
           ),
         );
    ```

    {{site.alert.note}}
      “Pascal命名法”（也称为“大写驼峰命名法”）意味着字符串中的每个单词（包括第一个单词）都以大写字母开头。因此，“uppercamelcase”变为“UpperCamelCase”。
    {{site.alert.end}}

 5. 如果应用程序正在运行，[热重载](/docs/get-started/test-drive)更新正在运行的应用程序。每次单击热重载或保存项目时，您应该在正在运行的应用程序中看到随机选择的不同单词对。这是因为单词对是在build方法中生成的，该方法在每次MaterialApp需要渲染时，或者在Flutter Inspector中切换平台时运行。

    {% indent %}
      {% include android-ios-figure-pair.md image="step2.png" alt="App at completion of second step" %}
    {% endindent %}

### 有问题？
{:.no_toc}

如果您的应用运行不正常，请查找拼写错误。如果需要，请使用以下链接中的代码重新回到正轨。

* [pubspec.yaml]({{code-url}}/startup_namer/step2_use_package/pubspec.yaml)
* [lib/main.dart]({{code-url}}/startup_namer/step2_use_package/lib/main.dart)

## 第3步：添加Stateful小部件

<?code-excerpt path-base="codelabs/startup_namer/step3_stateful_widget"?>

State<em>less</em>小部件是不可变的，这意味着它们的属性不能改变&mdash;所有值都是最终的。

State<em>ful</em>小部件维护可能在小部件生命周期内发生更改的状态。实现有状态小部件至少需要两个类：1）一个StatefulWidget类，它创建一个2）State类的实例。StatefulWidget类本身是不可变的，但State类在小部件的生命周期内持久存在。

在这一步中，你将添加一个有状态的小部件`RandomWords`，它创建其`State`类`RandomWordsState`。然后，您将在现有的`MyApp`无状态小部件中使用`RandomWords`作为子级。

 1. 创建一个最小的状态类。将以下内容添加到`main.dart`的底部：

    <?code-excerpt "lib/main.dart (RandomWordsState)" title region="RWS-class-only" plaster="// TODO Add build() method" indent-by="2"?>
    ```dart
      class RandomWordsState extends State<RandomWords> {
        // TODO Add build() method
      }
    ```

    注意声明`State<RandomWords>`。这表明我们正在使用专门用于`RandomWords`的通用[State]({{site.api}}/flutter/widgets/State-class.html)类。应用程序的大多数逻辑和状态都驻留在这里&mdash;它维护`RandomWords`小部件的状态。当用户通过切换心脏图标从列表中添加或删除它们时，此类保存生成的单词对（随着用户滚动而无限增长），以及最喜欢的单词对（在[第2部分]({{site.codelabs}}/codelabs/first-flutter-app-pt2)中）。

    `RandomWordsState`依赖`RandomWords`类。您接下来将添加。

 2. 将有状态的`RandomWords`小部件添加到`main.dart`。除了创建其State类之外，`RandomWords`小部件几乎没有其他功能：

    <?code-excerpt "lib/main.dart (RandomWords)" title indent-by="2"?>
    ```dart
      class RandomWords extends StatefulWidget {
        @override
        RandomWordsState createState() => RandomWordsState();
      }
    ```

    添加状态类后，IDE会抱怨该类缺少build方法。接下来，您将添加一个基本build方法，通过将单词生成代码从`MyApp`移动到`RandomWordsState`来生成单词对。

 3. 添加`build()`方法到`RandomWordsState`：

    <?code-excerpt "lib/main.dart (RandomWordsState)" title indent-by="2" replace="/(\n  )(.*)/$1[!$2!]/g"?>
    ```dart
      class RandomWordsState extends State<RandomWords> {
        [!@override!]
        [!Widget build(BuildContext context) {!]
        [!  final wordPair = WordPair.random();!]
        [!  return Text(wordPair.asPascalCase);!]
        [!}!]
      }
    ```

 4. 通过进行以下diff中显示的更改，从`MyApp`中删除单词生成代码：

    <?code-excerpt path-base="codelabs/startup_namer"?>
    <?code-excerpt "{step2_use_package,step3_stateful_widget}/lib/main.dart" to="}"?>
    ```diff
    --- step2_use_package/lib/main.dart
    +++ step3_stateful_widget/lib/main.dart
    @@ -6,7 +6,6 @@
     class MyApp extends StatelessWidget {
       @override
       Widget build(BuildContext context) {
    -    final wordPair = WordPair.random();
         return MaterialApp(
           title: 'Welcome to Flutter',
           home: Scaffold(
    @@ -14,8 +13,8 @@
               title: Text('Welcome to Flutter'),
             ),
             body: Center(
    -          child: Text(wordPair.asPascalCase),
    +          child: RandomWords(),
             ),
           ),
         );
       }
    ```

 5. 重启应用。应用程序应该像以前一样运行，每次热重载或保存应用程序时都会显示一个单词对。

{{site.alert.tip}}
  如果您在热重载时看到以下警告，请考虑重启应用程序：

  **Reloading...<br>
  Some program elements were changed during reload but did not run when
  the view was reassembled; you may need to restart the app (by pressing "R")
  for the changes to have an effect.**

  这可能是误报，但重启可确保您的更改反映在应用程序的UI中。
{{site.alert.end}}


### 有问题？
{:.no_toc}

如果您的应用运行不正常，您可以使用以下链接中的代码重新回到正轨。

* [lib/main.dart]({{code-url}}/startup_namer/step3_stateful_widget/lib/main.dart)

## 第4步：创建无限滚动的ListView

<?code-excerpt path-base="codelabs/startup_namer/step4_infinite_list"?>

在这一步中，您将扩展`RandomWordsState`以生成并显示单词对的列表。当用户滚动时，`ListView`小部件中显示的列表会无限增长。`ListView`的`builder`工厂构造函数允许您根据需要延迟构建列表视图。

 1. 将`_suggestions`列表添加到`RandomWordsState`类以保存建议的单词对。此外，添加`_biggerFont`变量以使字体更大。

    <?code-excerpt "lib/main.dart" title region="RWS-var" indent-by="2" replace="/final .*/[!$&!]/g"?>
    ```dart
      class RandomWordsState extends State<RandomWords> {
        [!final _suggestions = <WordPair>[];!]
        [!final _biggerFont = const TextStyle(fontSize: 18.0);!]
        // ···
      }
    ```

    {{site.alert.note}}
      Dart语言中，在标识符前面加下划线可以[加强隐私]({{site.dart-site}}/guides/language/language-tour)。
    {{site.alert.end}}

    接下来，您将向`RandomWordsState`类添加`_buildSuggestions()`函数。此方法构建`ListView`，显示建议的单词配对。

    `ListView`类提供了一个构建器属性`itemBuilder`，它是一个工厂构建器和指定为匿名函数的回调函数。两个参数传递给该函数&mdash;`BuildContext`和行迭代器`i`。迭代器从0开始，函数每次调用时递增。对于每个建议的单词对，它增加两次：一次用于ListTile，一次用于Divider。 此模型允许建议的列表在用户滚动时无限增长。

 2. 添加`_buildSuggestions()`函数到`RandomWordsState`类：

    <?code-excerpt "lib/main.dart (_buildSuggestions)" title indent-by="2"?>
    ```dart
      Widget _buildSuggestions() {
        return ListView.builder(
            padding: const EdgeInsets.all(16.0),
            itemBuilder: /*1*/ (context, i) {
              if (i.isOdd) return Divider(); /*2*/

              final index = i ~/ 2; /*3*/
              if (index >= _suggestions.length) {
                _suggestions.addAll(generateWordPairs().take(10)); /*4*/
              }
              return _buildRow(_suggestions[index]);
            });
      }
    ```

    {:.numbered-code-notes}
     1. 每个建议的单词对调用一次`itemBuilder`回调，并将每个建议单词对放入`ListTile`行。对于偶数行，该函数为单词对添加`ListTile`行。对于奇数行，该函数添加一个`Divider`小部件以在视觉上分隔条目。请注意，在较小的设备上可能难以看到分隔器。
     2. 在`ListView`中的每一行之前添加一个一像素高的分隔器小部件。
     3. 表达式`i ~/ 2`将`i`除以2并返回整数结果。例如：1,2,3,4,5变为0,1,1,2,2。这将计算`ListView`中实际的单词对数，减去分隔器小部件。
     4. 如果您已到达可用单词对的末尾，则再生成10个并将它们添加到建议列表中。

    `_buildSuggestions()`函数每个单词对调用一次`_buildRow()`。此函数在`ListTile`中显示每个新单词对，这使您可以在下一步中使行更具吸引力。

 3. 添加`_buildRow()`函数到`RandomWordsState`：

    <?code-excerpt "lib/main.dart (_buildRow)" title indent-by="2"?>
    ```dart
      Widget _buildRow(WordPair pair) {
        return ListTile(
          title: Text(
            pair.asPascalCase,
            style: _biggerFont,
          ),
        );
      }
    ```

 4. 在`RandomWordsState`类中，更新`build()`方法使用`_buildSuggestions()`，而不是直接调用单词生成库。
    （[Scaffold]({{site.api}}/flutter/material/Scaffold-class.html)实现了基本的Material Design可视化布局。）用突出显示的代码替换方法体：

    <?code-excerpt "lib/main.dart (build)" title region="RWS-build" replace="/(\n  )(return.*|  .*|\);)/$1[!$2!]/g" indent-by="2"?>
    ```dart
      @override
      Widget build(BuildContext context) {
        [!return Scaffold(!]
        [!  appBar: AppBar(!]
        [!    title: Text('Startup Name Generator'),!]
        [!  ),!]
        [!  body: _buildSuggestions(),!]
        [!);!]
      }
    ```

 5. 在`MyApp`类中，通过更改标题并将home更改为`RandomWords`小部件来更新`build()`方法：

    <?code-excerpt path-base="codelabs/startup_namer"?>
    <?code-excerpt "{step3_stateful_widget,step4_infinite_list}/lib/main.dart" diff-u="4" from="class MyApp" to="}"?>
    ```diff
    --- step3_stateful_widget/lib/main.dart
    +++ step4_infinite_list/lib/main.dart
    @@ -6,15 +6,8 @@
     class MyApp extends StatelessWidget {
       @override
       Widget build(BuildContext context) {
         return MaterialApp(
    -      title: 'Welcome to Flutter',
    -      home: Scaffold(
    -        appBar: AppBar(
    -          title: Text('Welcome to Flutter'),
    -        ),
    -        body: Center(
    -          child: RandomWords(),
    -        ),
    -      ),
    +      title: 'Startup Name Generator',
    +      home: RandomWords(),
         );
       }
    ```

 6. 重启应用。无论滚动多远，你都应该看到一个单词对列表。

    {% indent %}
      {% include android-ios-figure-pair.md image="step4-infinite-list.png" alt="App at completion of fourth step" %}
    {% endindent %}

### 有问题？
{:.no_toc}

如果您的应用运行不正常，您可以使用以下链接中的代码重新回到正轨。

* [lib/main.dart]({{code-url}}/startup_namer/step4_infinite_list/lib/main.dart)

{% include run-profile.md %}

## 接下来的步骤
{:.no_toc}

{% include app-figure.md class="site-image-right" img-class="border"
    image="get-started/startup-namer.gif" caption="来自第2部分的应用" %}

祝贺您！

您已经编写了一个可在iOS和Android上运行的交互式Flutter应用程序。在这个代码实验室中，你已经：

* 从头开始创建了一个Flutter应用程序。
* 编写了Dart代码。
* 利用了外部第三方库。
* 使用了热重载以加快开发周期。
* 实现了一个有状态的小部件。
* 创建了一个延迟加载的无限滚动列表。

如果您想扩展此应用，请继续[Google Developers Codelabs]({{site.codelabs}})网站的[第2部分]({{site.codelabs}}/codelabs/first-flutter-app-pt2)，在其中添加以下功能：

* 通过添加可点击的心脏图标来实现交互性，以保存喜欢的单词对。
* 通过添加包含已保存收藏夹的新屏幕，实现导航到新新路由。
* 修改主题颜色，制作全白的应用程序。
