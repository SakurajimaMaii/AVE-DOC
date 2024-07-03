# 概览

[![JDK Version](https://img.shields.io/badge/jdk%20version-17-2300b894?style=flat)](https://img.shields.io/badge/jdk%20version-17-2300b894)
[![GitHub license](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg?style=flat)](https://www.apache.org/licenses/LICENSE-2.0)

!!! tip "依赖更新说明"

    从 **1.3.1** 版本开始，日志核心库将作为独立的模块进行发布。

## 特性

- 支持插件化安装。
- 支持自定义日志打印格式。
- 支持显示日志位置用于快速定位。
- 支持显示当前打印的日志信息。
- 支持日志文件存储。
- 支持对象以 json(pretty 可选) 风格输出。
- 支持 JsonString 打印。

## 日志风格

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-core/#134)

目前提供了以下几种默认风格：

=== "表格风格"

    <div class="result" markdown>
    
    ![table_format](../img/table_format.png){ align=right width="500" }

    - 支持自定义日志头显示内容。
    - 支持限制每行字符数。
    - 支持限制打印次数。

    </div>

=== "线性风格"

    <div class="result" markdown>

    <figure markdown="span">
    ![log_desktop](../img/line_format.png){ width="500" }
    </figure>

    </div>

=== "多彩线性风格"

    <div class="result" markdown>

    ![log_desktop](../img/line_colorful_format.png){ align=right width="500" }

    - 提供了默认的控制台输出颜色。

    </div>

=== "简约模式"

    <div class="result" markdown>

    ![log_desktop](../img/only_msg_format.png){ align=right width="500" }

    - 仅保留日志内容本身不附加额外信息。

    </div>

## 面向 Tencent/Mars

## 面向 Okhttp

[:octicons-tag-24: Version 1.3.3](https://ave.entropy2020.cn/version/log-okhttp/#133)

```kotlin
private val mLogcat: LogCat = mLogFactory.getLogCat(OpenApi::class.java)
private val mOkhttp3Interceptor: Okhttp3Interceptor = Okhttp3Interceptor.getInstance(mLogcat)
```
<div class="result" markdown>

![log_okhttp](../img/log_okhttp.png){ align=right width="500" }

- 支持过滤请求。
- 支持自定义日志内容显示级别。
- 支持自定义请求日志级别。
- 支持自定义回复日志级别。
- 支持超长内容打印。

</div>

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

### log-okhttp

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-okhttp)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-okhttp:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-okhttp:$version")
    ```

### log-mars

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-mars)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-mars:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-mars:$version")
    ```
