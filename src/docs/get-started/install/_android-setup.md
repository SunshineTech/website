## Android设置

{{site.alert.note}}
  Flutter依赖Android Studio的完整安装来提供其Android平台依赖性。但是，您可以在许多编辑器中编写Flutter应用程序；后面的步骤将讨论这个问题。
{{site.alert.end}}

### 安装Android Studio

 1. 下载并安装[Android Studio]({{site.android-dev}}/studio)。
 1. 启动Android Studio，然后浏览“Android Studio安装向导”。这将安装最新的Android SDK，Android SDK Platform-Tools和Android SDK Build-Tools，这些都是Flutter在开发Android时所需要的。

### 设置您的Android设备

要准备在Android设备上运行和测试Flutter应用，您需要运行Android 4.1（API级别16）或更高版本的Android设备。

 1. 在您的设备上启用**开发人员选项**和**USB调试**。[Android文档]({{site.android-dev}}/studio/debug/dev-options)中提供了详细说明。
 1. 仅限Windows：安装[Google USB Driver]({{site.android-dev}}/studio/run/win-usb)
 1. 使用USB线将手机插入计算机。如果您的设备出现提示，请授权您的计算机访问您的设备。
 1. 在终端中，运行`flutter devices`命令以验证Flutter是否识别您连接的Android设备。

默认情况下，Flutter使用您的`adb`工具所基于的Android SDK版本。如果您希望Flutter使用Android SDK的其他安装，则必须将`ANDROID_HOME`环境变量设置为该安装目录。

### 设置Android模拟器

要准备在Android模拟器上运行和测试Flutter应用，请按以下步骤操作：

 1. 在计算机上启用[VM加速]({{site.android-dev}}/studio/run/emulator-acceleration)。
 1. 启动**Android Studio > Tools > Android > AVD Manager**并选择**Create Virtual Device**。（**Android**子菜单只在Android项目中出现。）
 1. 选择设备定义并选择**下一步**。
 1. 选择一个或多个想要模拟的Android版本的系统镜像，并选择**下一步**。推荐_x86_或_x86\_64_镜像。
 1. 在“仿真性能”下，选择**Hardware - GLES 2.0**以启用[硬件加速]({{site.android-dev}}/studio/run/emulator-acceleration)。
 1. 验证AVD配置是否正确，然后选择“完成”。

    有关上述步骤的详细信息，请参阅[管理AVD]({{site.android-dev}}/studio/run/managing-avds)。
 1. 在Android虚拟设备管理器中，单击工具栏中的**运行**。模拟器将启动并显示所选操作系统版本和设备的默认画布。
