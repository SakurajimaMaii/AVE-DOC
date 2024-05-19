# 概览

[![JDK Version](https://img.shields.io/badge/jdk%20version-17-2300b894?style=flat)](https://img.shields.io/badge/jdk%20version-17-2300b894)
[![GitHub license](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg?style=flat)](https://www.apache.org/licenses/LICENSE-2.0)

!!! tip "依赖更新说明"

    从 **1.3.1** 版本开始，日志核心库将作为独立的模块进行发布。

## 面向 Android 

![log_android](../img/log_android.png){ align=right width="400" }

- 支持自定义显示标题。
- 支持显示日志位置，用于快速定位。
- 支持显示当前日志的线程信息。
- 支持超长内容的打印。
- 支持日志文件存储。
- 支持对象以 json(pretty 可选) 风格输出。
- 支持 JsonString 打印。

## 面向 Kotlin/Java 程序

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

![log_desktop](../img/log_desktop.png){ align=left width="400" }

- **提供了默认的控制台输出颜色。**
- 支持显示日志位置，用于快速定位。
- 支持显示当前日志的线程信息。
- 支持日志文件存储，查看 [示例](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/libraries/log/desktop/log) 。
- 支持对象以 json(pretty 可选) 风格输出。
- 支持 JsonString 打印。

## 快速使用

### log-core

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-core)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-core:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-core:$version")
    ```

### log-desktop

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-desktop)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-desktop:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-desktop:$version")
    ```
