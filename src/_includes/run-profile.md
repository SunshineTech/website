## 配置文件运行

{{site.alert.important}}
  _不要_ 在启用调试和热重载的情况下测试应用程序的性能。
{{site.alert.end}}

到目前为止，您运行的应用程序处于调试模式，可以在较大的性能开销下实现更快的开发（例如，热重载）。因此，在这种模式下，会出现janky动画。要查看应用程序在发布时的执行情况，请尝试{{include.ide_profile}}以下终端命令。

```terminal
$ flutter run --profile
```

与调试模式下相比，动画应该更加平滑。
