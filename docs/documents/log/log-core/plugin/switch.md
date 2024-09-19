# 日志开关

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

[LogSwitch](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log.plugin/-log-switch/index.html) 提供了 `open` 参数，通过该参数可以控制全局的日志开关。

```kotlin
val logFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    .... 
}
```
