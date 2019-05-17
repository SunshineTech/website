## 获取Flutter SDK

 1. 下载以下安装包以获取Flutter SDK的最新{{site.sdk.channel}}版本：

    [(loading...)](#){:.download-latest-link-{{os}}.btn.btn-primary}

    对于其他发布渠道和旧版本，请参阅[SDK存档](/docs/development/tools/sdk/archive)页面。
 1. 解压缩zip文件并将包含的`flutter`放在Flutter SDK所需的安装位置（例如，`C:\src\flutter`；不要将Flutter安装在像`C:\Program Files\`这样要求提升特权的目录中）。
 1. 找到`flutter`目录中的`flutter_console.bat`文件。通过双击启动它。

您现在可以在Flutter控制台中运行Flutter命令了！

要更新现有版本的Flutter，请参阅[升级Flutter](/docs/development/tools/sdk/upgrading)。

### 更新你的路径

如果您希望在常规Windows控制台中运行Flutter命令，请执行以下步骤将Flutter添加到`PATH`环境变量中：

* 在“开始”搜索栏中，键入'env'并选择**为您的帐户编辑环境变量**
* 在**用户变量**下检查是否有名为**Path**的条目：
  * 如果该条目已存在，则使用`;`作为与现有值的分隔符，将完整路径附加到`flutter\bin`。
  * 如果该条目不存在，则创建一个名为`Path`的新用户变量，其中`flutter\bin`的完整路径为其值。

请注意，您必须关闭并重新打开任何现有控制台窗口才能使这些更改生效。

### 运行`flutter doctor`

从路径中具有Flutter目录（参见上文）的控制台窗口中，运行以下命令以查看是否存在完成设置所需的任何平台依赖项：

```console
C:\src\flutter>flutter doctor
```

此命令检查您的环境并显示Flutter安装状态的报告。仔细检查输出以了解您可能需要安装的其他软件或执行的其他任务（以**粗体**文本显示）。

例如：

<pre>
[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    <strong>✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ</strong>
    • Try re-installing or updating your Android SDK,
      visit {{site.url}}/setup/#android-setup for detailed instructions.
</pre>

以下部分描述了如何执行这些任务并完成设置过程。一旦安装了任何缺少的依赖项，就可以再次运行`flutter doctor`命令来验证是否已正确设置了所有内容。

{% include_relative _analytics.md %}
