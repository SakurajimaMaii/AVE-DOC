# 日志开关

[:octicons-tag-24: Version 1.3.1](https://sakurajimamaii.github.io/AVE-DOC/version/log-core/#131)

!!! tip "LogSwitch 行为改变提示"

    从 `1.3.8` 版本开始，用户只有安装 [LogSwitch](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-switch/index.html?query=class%20LogSwitch(val%20open:%20Boolean)) 才能够启用日志，默认情况下日志不会启用。

[LogSwitch](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log.plugin/-log-switch/index.html) 提供了 `open` 参数，通过该参数可以控制全局的日志开关。

```kotlin
val logFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    .... 
}
```
