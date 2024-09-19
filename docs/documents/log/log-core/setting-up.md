# 快速开始

## 添加依赖

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-core)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-core:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-core:$version")
    ```

## 创建 LogFactory

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

```kotlin
val logFactory: LogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    install(LogPrinter)
}
```

## 获取 Logcat 并打印日志

[:octicons-tag-24: Version 1.3.5](https://ave.entropy2020.cn/version/log-core/#135)

从该版本开始，用户无需调用 [getLogCat()](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-factory/get-log-cat.html) 
来获取 [LogCat](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-cat/index.html) 对象。

```kotlin
// 获取 Logcat
val logcat = logFactory("global")
```

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-core/#134)

```kotlin
// 获取 Logcat
val logcat = logFactory.getLogCat(LogCatTest::class.java)

// 打印日志
logcat.d("这是一条日志")
```
