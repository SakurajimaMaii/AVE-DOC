# 日志打印

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-desktop/#131)

如果想要在 Kotlin/Java 应用中启用日志打印，需要配置 [LogPrinter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-printer/index.html?query=class%20LogPrinter(val%20mConfiguration:%20LogPrinter.Configuration)) 插件，并调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 来获取 [DesktopLogger](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-logger/index.html) 。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter) {
        logger = Logger.desktop() // since 1.3.1
    }
}
```

以下是按照默认配置打印的日志格式：

<figure markdown>
  ![默认日志打印格式](../img/line_colorful_format.png)
  <figcaption>默认日志打印格式</figcaption>
</figure>
