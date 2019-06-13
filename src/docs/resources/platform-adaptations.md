---
title: 平台特定的行为和适配
---

## 适配哲学

一般有2个平台适配性案例：

1. 作为OS环境行为的事物（例如文本编辑和滚动），如果发生不同的行为则会“出错”。
2. 通常使用OEM的SDK在应用程序中实现的事物（例如在iOS上使用并行选项卡或在Android上显示[android.app.AlertDialog](https://developer.android.com/reference/android/app/AlertDialog.html)）。

本文主要介绍Flutter在Android和iOS上的案例1中提供的自动适配。

对于案例2，Flutter捆绑了产生平台约定的适当效果的方法，但在需要应用程序设计选择时不会自动适配。有关讨论，请参阅[#8410](https://github.com/flutter/flutter/issues/8410#issuecomment-468034023)。

## 页面导航

Flutter提供在Android和iOS上看到的导航模式，并自动将导航动画适配到当前平台。

### 导航转换

在**Android**上，默认的[Navigator.push]({{site.api}}/flutter/widgets/Navigator/push.html)转换是在[startActivity()](https://developer.android.com/reference/android/app/Activity.html#startActivity(android.content.Intent))之后建模的，它通常具有一个自底向上的动画变体。

在**iOS**上：

* 默认的[Navigator.push]({{site.api}}/flutter/widgets/Navigator/push.html) API会产生iOS Show/Push样式转换，该转换根据区域设置的RTL设置从端到端动画。 新路由背后的页面也会以与iOS中相同的方向视差滑动。
* 在推送[PageRoute.fullscreenDialog]({{site.api}}/flutter/widgets/PageRoute-class.html)为true的页面路径时，存在单独的自底向上转换样式。这表示iOS的Present/Modal样式转换，通常用于全屏模式页面。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img style="border-radius: 12px;" src="../../images/platform-adaptations/navigation-android.gif" class="figure-img img-fluid" alt="An animation of the bottom-up page transition on Android" />
        <figcaption class="figure-caption">
          Android页面转换
        </figcaption>
      </figure>
    </div>
    <div class="col-sm text-center">
      <figure class="figure">
        <img style="border-radius: 22px;" src="../../images/platform-adaptations/navigation-ios.gif" class="figure-img img-fluid" alt="An animation of the end-start style push page transition on iOS" />
        <figcaption class="figure-caption">
          iOS推送转换
        </figcaption>
      </figure>
    </div>
    <div class="col-sm text-center">
      <figure class="figure">
        <img style="border-radius: 22px;" src="../../images/platform-adaptations/navigation-ios-modal.gif" class="figure-img img-fluid" alt="An animation of the bottom-up style present page transition on iOS" />
        <figcaption class="figure-caption">
          iOS当前转换
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 特定于平台的转换细节

在**Android**上，根据您的操作系统版本存在2页转换动画样式：

* API 28前使用自底向上的动画，[向上滑动并淡入]({{site.api}}/flutter/material/FadeUpwardsPageTransitionsBuilder-class.html)。
* 在API 28及更高版本中，自底向上的动画[向上滑动和剪辑显示]({{site.api}}/flutter/material/OpenUpwardsPageTransitionsBuilder-class.html)。

在**iOS**上使用推送样式转换时，Flutter捆绑的[CupertinoNavigationBar]({{site.api}}/flutter/cupertino/CupertinoNavigationBar-class.html)和[CupertinoSliverNavigationBar]({{site.api}}/flutter/cupertino/CupertinoSliverNavigationBar-class.html)导航栏会自动将每个子组件设置动画为在下一页或上一页的CupertinoNavigationBar或CupertinoSliverNavigationBar上其对应的子组件。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img style="border-radius: 12px;" src="../../images/platform-adaptations/navigation-android.gif" class="figure-img img-fluid" alt="An animation of the page transition on Android pre-Android P" />
        <figcaption class="figure-caption">
          Android Pre-P
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img style="border-radius: 12px;" src="../../images/platform-adaptations/navigation-android-p.gif" class="figure-img img-fluid" alt="An animation of the page transition on Android on Android P" />
        <figcaption class="figure-caption">
          Android Post-P
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img style="border-radius: 22px;" src="../../images/platform-adaptations/navigation-ios-nav-bar.gif" class="figure-img img-fluid" alt="An animation of the nav bar transitions during a page transition on iOS" />
        <figcaption class="figure-caption">
          iOS导航栏
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 后退导航

在**Android**上，默认情况下，OS后退按钮被发送到Flutter并弹出[WidgetsApp]({{site.api}}/flutter/widgets/WidgetsApp-class.html)导航器的顶部路由。

在**iOS**上，可以使用边缘滑动手势来弹出顶部路由。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img style="border-radius: 12px;" src="../../images/platform-adaptations/navigation-android-back.gif" class="figure-img img-fluid" alt="A page transition triggered by the Android back button" />
        <figcaption class="figure-caption">
          Android后退按钮
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img style="border-radius: 22px;" src="../../images/platform-adaptations/navigation-ios-back.gif" class="figure-img img-fluid" alt="A page transition triggered by an iOS back swipe gesture" />
        <figcaption class="figure-caption">
          iOS后退滑动手势
        </figcaption>
      </figure>
    </div>
  </div>
</div>

## 滚动

滚动是平台外观的重要组成部分，Flutter会自动调整滚动行为来匹配当前平台。

### 物理模拟

Android和iOS都有复杂的滚动物理模拟，难以口头描述。一般来说，iOS的可滚动性具有更大的重量和动态摩擦，但Android具有更多的静态摩擦。因此，iOS逐渐获得高速，但突然停止较慢，在慢速时更加滑溜。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/scroll-soft.gif" class="figure-img img-fluid rounded" alt="A soft fling where the iOS scrollable slid longer at lower speed than Android" />
        <figcaption class="figure-caption">
          软抛对比
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/scroll-medium.gif" class="figure-img img-fluid rounded" alt="A medium force fling where the Android scrollable reached speed faster and stopped more abruptly after reaching a longer distance" />
        <figcaption class="figure-caption">
          中抛对比
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/scroll-strong.gif" class="figure-img img-fluid rounded" alt="A strong fling where the Android scrollable reach speed faster and reached significantly more distance" />
        <figcaption class="figure-caption">
          强抛对比
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 过度滚动行为

在**Android**上，滚过可滚动边缘会显示[过度滚动发光指示器]({{site.api}}/flutter/widgets/GlowingOverscrollIndicator-class.html)（基于当前Material主题的颜色）。

在**iOS**上，滚过可滚动边缘会[过度滚动]({{site.api}}/flutter/widgets/BouncingScrollPhysics-class.html)而阻力增加，然后快速恢复。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/scroll-overscroll.gif" class="figure-img img-fluid rounded" alt="Android and iOS scrollables being flung past their edge and exhibiting platform specific overscroll behavior" />
        <figcaption class="figure-caption">
          动态过度滚动比较
        </figcaption>
      </figure>
    </div>
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/scroll-static-overscroll.gif" class="figure-img img-fluid rounded" alt="Android and iOS scrollables being overscrolled from a resting position and exhibiting platform specific overscroll behavior" />
        <figcaption class="figure-caption">
          静态过度滚动比较
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 动量

在**iOS**上，同一方向上的重复抛掷会叠加动量，并在每次连续抛掷时建立更快的速度。**Android**上没有相同的行为。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/scroll-momentum-ios.gif" class="figure-img img-fluid rounded" alt="Repeated scroll flings building momentum on iOS" />
        <figcaption class="figure-caption">
          iOS滚动动量
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 回到顶部

在**iOS**上，点击操作系统状态栏会将主滚动控制器滚动到顶部位置。**Android**上没有相同的行为。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img style="border-radius: 22px;" src="../../images/platform-adaptations/scroll-tap-to-top-ios.gif" class="figure-img img-fluid" alt="Tapping the status bar scrolls the primary scrollable back to the top" />
        <figcaption class="figure-caption">
          iOS状态栏点击回到顶部
        </figcaption>
      </figure>
    </div>
  </div>
</div>

## 排版

使用Material包时，排版会自动默认为适合平台的字体系列。在Android上，使用Roboto字体。在iOS上，使用操作系统的旧金山字体系列。

使用Cupertino包时，[默认主题](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/cupertino/text_theme.dart)始终使用旧金山字体。

旧金山字体许可证将其使用限制为仅在iOS，macOS或tvOS上运行的软件。因此，如果平台被调试覆盖到iOS或使用默认的Cupertino主题，则在Android上运行时会使用后备字体。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/typography-android.png" class="figure-img img-fluid rounded" alt="Roboto font on Android" />
        <figcaption class="figure-caption">
          Android上的Roboto
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/typography-ios.png" class="figure-img img-fluid rounded" alt="San Francisco font on iOS" />
        <figcaption class="figure-caption">
          iOS上的旧金山
        </figcaption>
      </figure>
    </div>
  </div>
</div>

## 影像

使用Material包时，某些图标会根据平台自动显示不同的图形。例如，溢出按钮的3个点在iOS上是垂直的，在Android上是水平的。后退按钮在iOS上是简单V形，在Android上有一个杆/轴。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/iconography-android.png" class="figure-img img-fluid rounded" alt="Android appropriate icons" />
        <figcaption class="figure-caption">
          Android上的图标
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/iconography-ios.png" class="figure-img img-fluid rounded" alt="iOS appropriate icons" />
        <figcaption class="figure-caption">
          iOS上的图标
        </figcaption>
      </figure>
    </div>
  </div>
</div>

## 触觉反馈

Material和Cupertino包在某些情况下自动触发平台适当的触觉反馈。

例如，通过文本字段长按的单词选择会在Android上触发“嗡嗡”振动，而不会在iOS上触发。

在iOS上滚动选取器项目会触发“轻微影响”的敲击声，并且在Android上无反馈。

## 文本编辑

在编辑文本字段的内容时，Flutter还进行以下适配以匹配当前平台。

### 键盘手势导航

在**Android**上，可以在软键盘空格键上进行水平滑动，以在Material和Cupertino文本字段中移动光标。

在具有3D Touch功能的**iOS**设备上，可以在软键盘上进行强制按下拖动手势，以通过浮动光标在2D中移动光标。这适用于Material和Cupertino文本字段。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/text-keyboard-move-android.gif" class="figure-img img-fluid rounded" alt="Moving the cursor via the space key on Android" />
        <figcaption class="figure-caption">
          Android空间键光标移动
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/text-keyboard-move-ios.gif" class="figure-img img-fluid rounded" alt="Moving the cursor via 3D Touch drag on the keyboard on iOS" />
        <figcaption class="figure-caption">
          iOS 3D Touch拖动光标移动
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 文本选择工具栏

使用**Android上的Material**，在文本字段中进行文本选择时，将显示Android样式选择工具栏。

使用**iOS上的Material**或使用**Cupertino**，在文本字段中进行文本选择时，会显示iOS样式选择工具栏。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/text-toolbar-android.png" class="figure-img img-fluid rounded" alt="Android appropriate text toolbar" />
        <figcaption class="figure-caption">
          Android文本选择工具栏
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/text-toolbar-ios.png" class="figure-img img-fluid rounded" alt="iOS appropriate text toolbar" />
        <figcaption class="figure-caption">
          iOS文本选择工具栏
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 单击手势

使用**Android上的Material**，在文本字段中单击即可将光标放在点击位置。

折叠的文本选择还显示可拖动的句柄，以便随后移动光标。

使用**iOS上的Material**或使用**Cupertino**，在文本字段中单击即可将光标放在单击单词的最近边缘。

折叠的文本选择在iOS上没有可拖动的句柄。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/text-single-tap-android.gif" class="figure-img img-fluid rounded" alt="Moving the cursor to the tapped position on Android" />
        <figcaption class="figure-caption">
          Android tap
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/text-single-tap-ios.gif" class="figure-img img-fluid rounded" alt="Moving the cursor to the nearest edge of the tapped word on iOS" />
        <figcaption class="figure-caption">
          iOS tap
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 长按手势

使用**Android上的Material**，长按可选择长按下的单词。选择工具栏在释放时显示。

使用**iOS上的Material**或使用**Cupertino**，长按会将光标放在长按的位置。选择工具栏在释放时显示。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/text-long-press-android.gif" class="figure-img img-fluid rounded" alt="Selecting a word via long press on Android" />
        <figcaption class="figure-caption">
          Android长按
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/text-long-press-ios.gif" class="figure-img img-fluid rounded" alt="Selecting a position via long press on iOS" />
        <figcaption class="figure-caption">
          iOS长按
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 长按拖动手势

使用**Android上的Material**，长按同时拖动会扩展单词选择。

使用**iOS上的Material**或使用**Cupertino**，长按同时拖动会移动光标。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/text-long-press-drag-android.gif" class="figure-img img-fluid rounded" alt="Expanding word selection via long press drag on Android" />
        <figcaption class="figure-caption">
          Android长按拖动
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/text-long-press-drag-ios.gif" class="figure-img img-fluid rounded" alt="Moving the cursor via long press drag on iOS" />
        <figcaption class="figure-caption">
          iOS长按拖动
        </figcaption>
      </figure>
    </div>
  </div>
</div>

### 双击手势

在Android和iOS上，双击选择接收双击的单词并显示选择工具栏。

<div class="container">
  <div class="row">
    <div class="col-sm text-center">
      <figure class="figure">
        <img src="../../images/platform-adaptations/text-double-tap-android.gif" class="figure-img img-fluid rounded" alt="Selecting a word via double tap on Android" />
        <figcaption class="figure-caption">
          Android双击
        </figcaption>
      </figure>
    </div>
    <div class="col-sm">
      <figure class="figure text-center">
        <img src="../../images/platform-adaptations/text-double-tap-ios.gif" class="figure-img img-fluid rounded" alt="Selecting a word via double tap on iOS" />
        <figcaption class="figure-caption">
          iOS双击
        </figcaption>
      </figure>
    </div>
  </div>
</div>
