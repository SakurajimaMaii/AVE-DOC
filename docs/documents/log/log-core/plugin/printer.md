# 日志打印

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

[LogPrinter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-printer/index.html?query=class%20LogPrinter(val%20mConfiguration:%20LogPrinter.Configuration)) 允许你自定义日志打印级别和日志的打印样式。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter)
}
```

## 添加依赖

### [Tencent/XLog](https://github.com/Tencent/mars)

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-mars)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-mars:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-mars:$version")
    ```

### [VastTools](https://github.com/SakurajimaMaii/Android-Vast-Extension)

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/VastTools)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:VastTools:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:VastTools:$version")
    ```

### [log-desktop](https://github.com/SakurajimaMaii/Android-Vast-Extension)

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-desktop)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-desktop:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-desktop:$version")
    ```

## 设置允许打印的日志等级

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

通过设置 `level` 可以指定打印的日志的最小等级。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter){
        level = LogLevel.WARN
    }
}
```

!!! warning "level 过时说明"

    考虑到 `level` 对于日志等级的过滤不够灵活，因此在 [1.3.4](https://ave.entropy2020.cn/version/log-core/#134) 版本开始使用 `levelSet` 进行替代。

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-core/#134)

通过设置 `levelSet` 可以指定那些等级的日志可以被打印。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter){
        levelSet = setOf(LogLevel.VERBOSE)
    }
}
```

## 设置 Logger

### [Tencent/XLog](https://github.com/Tencent/mars)

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

调用 [mars()](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 获取 [MarsLogger](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/-mars-logger/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/log/log-mars/usage/) 。

```kotlin
// 指定日志的存储位置
val logDir = File(FileMgr.appInternalFilesDir(), "log")
val logCache = File(FileMgr.appInternalFilesDir(), "log-cache")

val mLogFactory: LogFactory = getLogFactory {
    // 配置插件
    install(LogPrinter) {
        logger = Logger.mars(logDir, logCache)
    }
}
```

!!! note "补充说明"

    注意，如果你使用 [Tencent/XLog](https://github.com/Tencent/mars) ，那么它集成了打印和存储。这点需要注意。

### [VastTools](https://github.com/SakurajimaMaii/Android-Vast-Extension)

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/VastTools/#131)

调用 [android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 获取 [AndroidLogger](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/-android-logger/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/VastTools/log/logger/) 。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    // 配置插件
    install(LogPrinter) {
        logger = Logger.android()
    }
}
```

### [log-desktop](https://github.com/SakurajimaMaii/Android-Vast-Extension)

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-desktop/#131)

调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 获取 [DesktopLogger](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-logger/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/log/log-desktop/logger/) 。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter) {
        logger = Logger.desktop()
    }
}
```