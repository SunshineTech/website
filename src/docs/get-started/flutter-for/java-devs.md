---
title: 从Java到Dart
description: Java开发人员的Dart介绍
---

## 介绍

Dart是Flutter的编程语言，Flutter是来自Google的移动应用SDK。 此代码实验室向您介绍Dart，重点介绍Java开发人员可能不期望的功能。

您可以在1分钟内编写Dart函数，在5分钟内编写脚本，在10分钟内编写应用程序！

### 您将学到什么

* 如何创建构造函数
* 指定参数的不同方式
* 何时以及如何创建getter和setter
* Dart如何处理隐私
* 如何创建工厂
* Dart中函数式编程的工作原理
* 其他核心Dart概念

### 您将需要什么

要完成此代码实验室，您只需要一个浏览器！

您将在[DartPad](https://www.dartlang.org/tools/dartpad)中编写和运行所有示例，DartPad是一种基于浏览器的交互式工具，可让您使用Dart语言功能和核心库。如果您愿意，可以使用IDE，例如WebStorm，带有Dart插件的IntelliJ或带有[Dart代码扩展](https://marketplace.visualstudio.com/items?itemName=Dart-Code.dart-code)的Visual Studio Code。

## 创建一个简单的Dart类

您将首先构建一个简单的Dart类，其功能与Java教程中的[Bicycle](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)类相同。Bicycle类包含一些带有getter和setter的私有实例变量。`main()`方法实例化Bicycle并将其打印到控制台。

### 启动DartPad

此代码实验室为每组练习提供了一个新的DartPad实例。下面的链接打开一个新实例，其中包含一个默认的“Hello”示例。您可以在整个代码实验室中继续使用相同的DartPad，但如果单击`Reset`按钮，DartPad会将您带回默认示例，从而丢失您的工作。

为方便起见，每个代码实验室页面顶部都有一个DartPad实例，它反映了每个练习开始时的状态。

[打开DartPad](https://dartpad.dartlang.org/0ca5b334ec413c084575f575e0240501?_blank)

请注意，DartPad会立即运行其代码。

### 定义Bicycle类

在`main()`函数上方，添加一个带有三个实例变量的`Bicycle`类。同时从`main()`中删除内容，如下所示：

    <?code-excerpt title?>
    ```dart
    class Bicycle {
      int cadence;
      int speed;
      int gear;
    }

    void main() {
    }
    ```

#### 观察
{:.no_toc}

* Dart的main方法名为`main()`或（如果需要访问命令行参数）`main(List<String> args)`。
* `main()`方法位于顶层。在Dart中，您可以在类之外定义代码。变量，函数，getter和setter都可以位于类之外。
* 原始Java示例使用`private`标签声明私有实例变量，Dart不使用它。您将在“第3步：添加只读变量”中了解有关隐私的更多信息。
* `main()`和Bicycle都没有声明为`public`，因为默认情况下所有标识符都是公共的。Dart没有`public`，`private`或`protected`关键字。
* Dart约定使用2个字符的缩进，而不是4个。由于一个名为[dartfmt](https://github.com/dart-lang/dart_style#readme)的方便工具，你不需要担心Dart的空白约定。 正如Dart代码约定（[Effective Dart](https://www.dartlang.org/guides/language/effective-dart)）所说，“Dart的官方空白处理规则是dartfmt产生的。”

#### 定义Bicycle构造函数

将以下构造函数添加到Bicycle类：

    <?code-excerpt title?>
    ```dart
    Bicycle(this.cadence, this.speed, this.gear);
    ```

##### 观察
{:.no_toc}

* 此构造函数没有主体，这在Dart中有效。
* 如果在无主体构造函数末尾忘记了分号（`;`），DartPad显示错误：“A function body must be provided.”。
* 在构造函数的参数列表中使用`this`是一个方便的快捷方式，用于为实例变量赋值。
* 上面的代码等同于以下内容：

    <?code-excerpt title?>
    ```dart
    Bicycle(int cadence, int speed, int gear) {
      this.cadence = cadence;
      this.speed = speed;
      this.gear = gear;
    }
    ```

#### 格式化代码

通过单击DartPad UI顶部的**Format**，随时重新格式化Dart代码。当您将代码粘贴到DartPad并且对正（justification）关闭时，重新格式化特别有用。

#### 实例化并打印Bicycle实例

将以下代码添加到`main()`函数中：

    <?code-excerpt title?>
    ```dart
    void main() {
      var bike = new Bicycle(2, 0, 1);
      print(bike);
    }
    ```

删除可选的`new`关键字：

    <?code-excerpt title?>
    ```dart
    var bike = Bicycle(2, 0, 1);
    ```

##### 观察
{:.no_toc}

* Dart 2中，`new`关键字变成可选的。
* 如果知道变量的值不会改变，可以使用`final`而不是`var`。

#### 运行示例

单击DartPad窗口顶部已启用的**Run**按钮来执行该示例。如果**Run**未启用，请参阅下面的**Problems**部分。

您应该看到以下输出：

    <?code-excerpt title?>
    ```dart
    Instance of 'Bicycle'
    ```

##### 观察
{:.no_toc}

* 不应出现任何错误或警告，表明类型推断正在起作用，并且分析器推断出`var bike = ...`定义了一个Bicycle实例。

#### 改善输出

虽然输出“Instance of ‘Bicycle'”是正确的，但它的信息量不大。所有Dart类都有一个`toString()`方法，您可以覆盖该方法以提供更有用的输出。

将以下`toString()`方法添加到Bicycle类中的任何地方：

    <?code-excerpt title?>
    ```dart
    @override
    String toString() => 'Bicycle: $speed mph';
    ```

##### 观察
{:.no_toc}

* `@override`注解告诉分析器您有意覆盖成员。如果您未能正确执行覆盖，分析器会引发错误。
* 在指定字符串时，Dart支持单引号或双引号。
* 使用字符串插值将表达式的值放在字符串文字中：`${expression}`。如果表达式是标识符，则可以跳过大括号：`$variableName`。
* 使用胖箭头（`=>`）表示法缩短单行函数或方法。

#### 运行示例

单击**Run**，现在应该看到以下输出：

    <?code-excerpt title?>
    ```dart
    Bicycle: 0 mph
    ```

##### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/f176b4c31b4be8a454107d0946fe2fa3?_blank)

### 添加只读变量

原始Java示例将`speed`定义为只读变量&mdash;它将其声明为`private`并仅提供getter。接下来，您将在Dart中提供相同的功能。

[在DartPad中打开bicycle.dart](https://dartpad.dartlang.org/f176b4c31b4be8a454107d0946fe2fa3?_blank)（或继续使用您的副本）

要将Dart标识符标记为其库私有的，请使用下划线（`_`）开始其名称。您可以通过更改名称和添加getter将`speed`转换为只读。

#### 使speed成为私有的只读实例变量

 1. 在Bicycle构造函数中，删除`speed`参数：

    <?code-excerpt title?>
    ```dart
    Bicycle(this.cadence, this.gear);
    ```

 2. 在`main()`中，从对Bicycle构造函数的调用中删除第二个参数（`speed`）：

    <?code-excerpt title?>
    ```dart
    var bike = Bicycle(2, 1);
    ```

 3. 将其余的`speed`更改为`_speed`。（2个地方）

    {{site.alert.tip}}
      如果您使用的是JetBrains IDE，则可以通过右键单击名称并从弹出菜单中选择**Refactor > Rename...**来同时重命名变量的所有实例。
    {{site.alert.end}}

  a. 初始化`_speed`为0：

    <?code-excerpt title?>
    ```dart
    int _speed = 0;
    ```

  b. 将以下getter添加到Bicycle类：

    <?code-excerpt title?>
    ```dart
    int get speed => _speed;
    ```

##### 观察
{:.no_toc}

* 未初始化变量（即使数字）的值为`null`。
* Dart编译器对任何以下划线为前缀的标识符强制实施隐私。
* 默认情况下，Dart为所有公共实例变量提供隐式getter和setter。除非要强制只读或只写变量，计算或验证值或在其他位置更新值，否则无需定义自己的getter/setter。
* 由于在[原始Java示例](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)中为`cadence`和`gear`提供了getter和setter，因此根据定义，它们在Dartiverse中不被认为是私有的。可以使用`bike.gear`或`bike.cadence`访问这些实例变量。
* 你可以从一个简单的字段开始，比如`bike.cadence`，然后重构它以使用getter和setter。API保持不变。换句话说，从字段到getter/setter并不是Dart的重大改变。

#### 完成将speed实现为只读实例变量

将以下方法添加到Bicycle类：

    <?code-excerpt title?>
    ```dart
    void applyBrake(int decrement) {
      _speed -= decrement;
    }

    void speedUp(int increment) {
      _speed += increment;
    } 
    ```

最后的Dart示例看起来与[原始Java](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)类似，但是只有23行而不是40行更紧凑：

    <?code-excerpt title?>
    ```dart
    class Bicycle {
      int cadence;
      int _speed = 0;
      int get speed => _speed;
      int gear;

      Bicycle(this.cadence, this.gear);

      void applyBrake(int decrement) {
        _speed -= decrement;
      }

      void speedUp(int increment) {
        _speed += increment;
      }

      @override
      String toString() => 'Bicycle: $_speed mph';
    }

    void main() {
      var bike = Bicycle(2, 1);
      print(bike);
    }
    ```

##### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/a81cf6bde4d52bb8b774d87aff842b56?_blank)

## 使用可选参数（而不是重载）

下一个练习定义了一个[Rectangle类](https://docs.oracle.com/javase/tutorial/java/javaOO/objectcreation.html)，这是Java教程中的另一个示例。

Java代码显示了重载构造函数，这是Java中的一种常见做法，其中构造函数具有相同的名称，但参数的数量或类型不同。Dart不支持重载构造函数并以不同方式处理这种情况，您将在本节中看到。

[在DartPad中打开Rectangle示例](https://dartpad.dartlang.org/68fb4923eee0e9e3d3af42730c1d3503?_blank)

### 添加Rectangle构造函数

添加一个空构造函数，替换Java示例中的所有四个构造函数：

    <?code-excerpt title?>
    ```dart
    Rectangle({this.origin = const Point(0, 0), this.width = 0, this.height = 0}); 
    ```

此构造函数使用可选的命名参数。

#### 观察
{:.no_toc}

* `this.origin`，`this.width`和`this.height`使用简写技巧在构造函数的声明中分配实例变量。
* `this.origin`，`this.width`和`this.height`是可选的命名参数。命名参数用大括号（`{}`）括起来。
* `this.origin = const Point(0, 0)`语法指定实例变量`origin`的默认值`Point(0,0)`。指定的默认值必须是编译时常量。此构造函数为所有三个实例变量提供默认值。

### 改善输出

将以下`toString()`函数添加到Rectangle类：

    <?code-excerpt title?>
    ```dart
    @override
    String toString() =>
          'Origin: (${origin.x}, ${origin.y}), width: $width, height: $height';
    ```

### 使用构造函数

使用以下代码替换`main()`以验证您是否可以仅使用所需的参数来实例化Rectangle。

    <?code-excerpt title?>
    ```dart
    @override
    main() {
      print(Rectangle(origin: const Point(10, 20), width: 100, height: 200));
      print(Rectangle(origin: const Point(10, 10)));
      print(Rectangle(width: 200));
      print(Rectangle());
    }
    ```

#### 观察
{:.no_toc}

* 与Java版本中等效构造函数的16行代码相比，Rectangle的Dart构造函数是一行代码。

### 运行示例

您应该看到以下输出：

    <?code-excerpt title?>
    ```dart
    Origin: (10, 20), width: 100, height: 200
    Origin: (10, 10), width: 0, height: 0
    Origin: (0, 0), width: 200, height: 0
    Origin: (0, 0), width: 0, height: 0
    ```

#### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/bdc6a0c88482c4492912cc2849aa5121?_blank)

## 创建工厂

工厂是Java中常用的设计模式，与直接对象实例化相比具有几个优点，例如隐藏实例化的细节，提供返回工厂返回类型的子类型的能力，以及可选地返回现有对象而不是新对象。

此步骤演示了两种实现形状创建工厂的方法：

* 选项1：创建顶级函数
* 选项2：创建工厂构造函数

在本练习中，您将使用Shapes示例，该示例实例化形状并打印其计算面积：


    <?code-excerpt title?>
    ```dart
    import 'dart:math';

    abstract class Shape {
      num get area;
    }

    class Circle implements Shape {
      final num radius;
      Circle(this.radius);
      num get area => pi * pow(radius, 2);
    }

    class Square implements Shape {
      final num side;
      Square(this.side);
      num get area => pow(side, 2);
    }

    main() {
      final circle = Circle(2);
      final square = Square(2);
      print(circle.area);
      print(square.area);
    }
    ```

[在DartPad中打开Shapes示例](https://dartpad.dartlang.org/a98247f43448f5e0eac4c7f483c173a5?_blank)

在控制台区域中，您应该看到圆形和正方形的计算面积：

    <?code-excerpt title?>
    ```dart
    12.566370614359172
    4
    ```

#### 观察
{:.no_toc}

* Dart支持抽象类。
* 您可以在一个文件中定义多个类。
* dart:math是Dart的核心库之一。其他核心库包括dart:core，dart:async，dart:convert和dart:collection。
* 在Dart 1.x中，核心库常量是大写的（PI）;在Dart 2中，它们是小写的（pi）。
* 此代码包含两个计算值的getter：

    <?code-excerpt title?>
    ```dart
    num get area => pi * pow(radius, 2); // Circle
    num get area => pow(side, 2); // Square
    ```

### 选项1：创建顶级函数

 1. 通过在最高级别（任何类之外）添加以下函数，将工厂实现为顶级函数：

    <?code-excerpt title?>
    ```dart
    Shape shapeFactory(String type) {
      if (type == 'circle') return Circle(2);
      if (type == 'square') return Square(2);
      throw 'Can\'t create $type.';
    }
    ```

 2. 通过替换main()方法中的前两行来调用工厂函数：

    <?code-excerpt title?>
    ```dart
    final circle = shapeFactory('circle');
    final square = shapeFactory('square');
    ```

#### 运行示例

输出应该与以前一样。

#### 观察
{:.no_toc}

* 如果使用除`'circle'`或`'square'`之外的任何字符串调用该函数，则会抛出异常。
* Dart SDK定义了许多常见异常类，或者您可以扩展Exception类以创建自己的更具体的异常，或者（如本示例中）您可以抛出描述遇到的问题的字符串。
* 遇到异常时，DartPad会报告`Uncaught`。要查看更有用的信息，请将代码包装在`try-catch`语句中，然后打印异常。作为可选练习，请查看此[DartPad示例](https://dartpad.dartlang.org/63e040a3fd682e191af40f6427eaf9ef?_blank)。
* 要在字符串中使用单引号，请使用斜杠（`'Can\'t create $type.'`）来转义嵌入的引号，或者使用双引号指定字符串（`"Can't create $type."`）。

#### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/a6abf3864fcd73a4400b8155f624d899?_blank)

### 选项2：创建工厂构造函数

使用Dart的`factory`关键字来创建工厂构造函数。

 1. 添加一个工厂构造函数到抽象的Shape类

    <?code-excerpt title?>
    ```dart
    abstract class Shape {
      factory Shape(String type) {
        if (type == 'circle') return Circle(2);
        if (type == 'square') return Square(2);
        throw 'Can\'t create $type.';
      }
      num get area;
    }
    ```

 2. 使用以下代码替换main()的前两行以实例化形状：

    <?code-excerpt title?>
    ```dart
    final circle = Shape('circle');
    final square = Shape('square');
    ```

 3. 删除先前添加的`shapeFactory()`函数。

#### 观察
{:.no_toc}

* 工厂构造函数中的代码与`shapeFactory()`函数中使用的代码相同。

#### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/8e2ad295a1b7c8254414afb43fc7d280?_blank)

## 实现接口

Dart语言不包含`interface`关键字，因为**每个类都定义了一个接口**。

 1. [在DartPad中打开Shapes示例](https://dartpad.dartlang.org/8e2ad295a1b7c8254414afb43fc7d280?_blank)（或继续使用您的副本）

 2. 添加扩展Circle类的CircleMock类：

    <?code-excerpt title?>
    ```dart
    class CircleMock implements Circle {}
    ```

 3. 您应该看到"Missing concrete implementations"错误。通过定义`area`和`radius`实例变量来修复此错误：

     <?code-excerpt title?>
    ```dart
    class CircleMock implements Circle {
      num area;
      num radius;
    }
    ```

### 观察
{:.no_toc}

* 即使CircleMock类没有定义任何行为，它也是有效的Dart——分析器不会引发任何错误。

### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/410028aef33e1157f7c7d78a8b67b419?_blank)

## 使用Dart进行函数式编程

在函数式编程中，您可以执行以下操作：

* 将函数作为参数传递。
* 将函数分配给变量。
* 将接收多个参数的函数解构为一系列函数（每个函数接收一个参数）。
* 创建一个可以用作常量值的无名函数（也称为 _lambda表达式_；在[JDK 8发行版](http://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html)中将lambda表达式添加到Java中）。


Dart支持所有这些功能。在Dart中，甚至函数是对象，并且具有类型Function。这意味着函数可以分配给变量或作为参数传递给其他函数。您也可以像调用函数一样调用Dart类的实例，如[此例](https://dartpad.dartlang.org/405379bacf30335f3aed)所示。

以下示例使用命令式（非函数式）代码：

    <?code-excerpt title?>
    ```dart
    String scream(int length) => "A${'a' * length}h!";

    main() {
      final values = [1, 2, 3, 5, 10, 50];
      for (var length in values) {
        print(scream(length));
      }
    }
    ```

[在DartPad中打开Scream示例](https://dartpad.dartlang.org/9bcb7dba6dca46e2a9dbfb300298461e?_blank)

输出应如下所示：

    <?code-excerpt title?>
    ```dart
    Aah!
    Aaah!
    Aaaah!
    Aaaaaah!
    Aaaaaaaaaaah!
    Aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaah!
    ```

### 观察
{:.no_toc}

* 使用字符串插值时，字符串`${'a' * length}`的计算结果为“字符`'a'`重复`length`次。”

### 将命令式代码转换为函数式

删除`main()`的`for() {...}`循环命令，并用一行使用方法链的代码替换它：

    <?code-excerpt title?>
    ```dart
    values.map(scream).forEach(print);
    ```

#### 运行示例

函数式方法打印出与命令式示例相同的六个“尖叫”。

#### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/368c0634feb20f47011f435d911456c2?_blank)

### 使用更多Iterable功能

来自dart:collection的List和Iterable支持`fold`、`where`、`join`、`skip`等。Dart还支持Map和Set。

使用以下语句替换`main()`中的`values.map()`行：

    <?code-excerpt title?>
    ```dart
    values.skip(1).take(3).map(scream).forEach(print);
    ```

#### 运行示例

输出应如下所示：

    <?code-excerpt title?>
    ```dart
    Aaah!
    Aaaah!
    Aaaaaah!
    ```

#### 观察
{:.no_toc}

* `skip(1)`跳过`values`列表文字中的第一个值1。
* `take(3)`获取`values`列表文字中接下来的3个值——2，3和5。
* 其余值跳过。

#### 有问题？
{:.no_toc}

[检查您的代码](https://dartpad.dartlang.org/bd0d627c9af8d264c2b3dde7c0939375?_blank)

## 祝贺！

在完成此代码实验室时，您已经获得了Java和Dart之间的一些差异的知识。Dart易于学习，此外，它的[核心库](https://www.dartlang.org/guides/libraries/useful-libraries)和[丰富的可用包](https://pub.dartlang.org/)可以提高您的工作效率。Dart适用于大型应用。数百名Google工程师使用Dart编写关键任务应用程序，这些应用程序带来了Google的大部分收入。

### 接下来的步骤

20分钟的代码实验室不足以向您展示Java和Dart之间的所有差异。 例如，此代码实验室未涵盖：

* async/await，它允许您编写异步代码，就好像它是同步的一样。看看这个[DartPad示例](https://dartpad.dartlang.org/fae22cffa7b184b4d27cd96dd633a5af?_blank)动画计算π的前5位小数。
* 方法级联， [一切都是构建器](http://news.dartlang.org/2012/02/method-cascades-in-dart-posted-by-gilad.html?_blank)！
* [空感知运算符](http://news.dartlang.org/2015/08/dart-112-released-with-null-aware.html?_blank)

如果您希望看到Dart技术的实际应用，请尝试使用[Flutter代码实验室](https://codelabs.developers.google.com/?cat=Flutter?_blank)。

### 了解更多

#### 文章

* [Flutter为什么使用Dart](https://hackernoon.com/why-flutter-uses-dart-dd635a054ebf)
* [宣布Dart 2：针对客户端开发进行优化](https://medium.com/dartlang/announcing-dart-2-80ba01f43b6)
* [我为什么从Java转向Dart](https://hackernoon.com/why-i-moved-from-java-to-dart-8f3802b1d652)

#### 资源

* [Dart语言之旅](https://www.dartlang.org/guides/language/language-tour)
* [Dart库之旅](https://www.dartlang.org/guides/libraries/library-tour)
* [Effective Dart](https://www.dartlang.org/guides/language/effective-dart)

#### 网站

* Dart语言：[www.dartlang.org](https://www.dartlang.org/)
* 用于Web的Dart，包含AngularDart：[webdev.dartlang.org](https://webdev.dartlang.org/)
* Flutter移动应用SDK：[flutter.io](https://flutter.io/)