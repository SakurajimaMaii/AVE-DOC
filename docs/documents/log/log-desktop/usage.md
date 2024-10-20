# 概述

!!! example "SLF4J 支持现已推出预览版"

    如果你的应用使用 [SLF4J](https://www.slf4j.org/) 作为日志门面，可以尝试使用 [log-slf4j](https://ave.entropy2020.cn/documents/log/log-slf4j/usage/) 。

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-desktop/#131)

如果想要在 Kotlin/Java 应用中启用日志打印，需要配置 [LogPrinter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-printer/index.html?query=class%20LogPrinter(val%20mConfiguration:%20LogPrinter.Configuration)) 插件，并调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 来获取 [DesktopLogger](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-logger/index.html) 。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter) {
        logger = Logger.desktop() 
    }
}
```

<div class="result" markdown>
<figure markdown>
  ![多彩线性风格示例](../img/line_colorful_format.png)
</figure>
</div>

## 添加依赖 

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-desktop)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-desktop:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-desktop:$version")
    ```
