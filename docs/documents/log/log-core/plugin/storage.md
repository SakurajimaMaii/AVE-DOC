# 日志存储

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

[LogStorage](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-storage/index.html) 允许你自定义日志的存储方式。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter)
}
```
