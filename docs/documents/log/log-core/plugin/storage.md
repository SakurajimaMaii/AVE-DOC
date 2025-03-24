# 日志存储

[:octicons-tag-24: Version 1.3.1](https://sakurajimamaii.github.io/AVE-DOC/version/log-core/#131)

[LogStorage](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-storage/index.html) 允许你自定义日志的存储方式。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogStorage)
}
```

## 添加依赖

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

## 设置允许保存的日志等级

!!! warning "level 过时说明"

    考虑到 `level` 对于日志等级的过滤不够灵活，因此在 [1.3.4](https://sakurajimamaii.github.io/AVE-DOC/version/log-core/#134) 版本开始使用 `levelSet` 进行替代。

[:octicons-tag-24: Version 1.3.4](https://sakurajimamaii.github.io/AVE-DOC/version/log-core/#134)

通过设置 `levelSet` 可以指定那些等级的日志可以被存储。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter){
        levelSet = setOf(LogLevel.VERBOSE)
    }
}
```

[:octicons-tag-24: Version 1.3.1](https://sakurajimamaii.github.io/AVE-DOC/version/log-core/#131)

通过设置 `level` 可以指定保存的日志的最小等级。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter){
        level = LogLevel.WARN
    }
}
```

## 设置 logStore

### [VastTools](https://github.com/SakurajimaMaii/Android-Vast-Extension)

[:octicons-tag-24: Version 1.3.1](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#131)

调用 [android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 获取 [AndroidStore](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/-android-store/index.html) ，具体使用请参考 [链接](https://sakurajimamaii.github.io/AVE-DOC/documents/VastTools/log/store/) 。

```kotlin
val logFactory: LogFactory = getLogFactory {
    // 配置插件
    install(LogStorage) {
        logStore = LogStore.android()
    }
}
```

### [log-desktop](https://github.com/SakurajimaMaii/Android-Vast-Extension)

[:octicons-tag-24: Version 1.3.1](https://sakurajimamaii.github.io/AVE-DOC/version/log-desktop/#131)

调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 获取 [DesktopLogger](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-logger/index.html) ，具体使用请参考 [链接](https://sakurajimamaii.github.io/AVE-DOC/documents/log/log-desktop/store/) 。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogStorage) {
        logStore = LogStore.desktop("", 1024L * 1000)
    }
}
```
