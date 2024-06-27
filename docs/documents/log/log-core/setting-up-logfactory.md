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
val mLogFactory: LogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    install(LogPrinter)
}
```

## 获取 Logcat 并打印日志

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-core/#134)

```kotlin
// 获取 Logcat
val logCat = mLogFactory.getLogCat(LogCatTest::class.java)

// 打印日志
logCat.d("这是一条日志")
```
