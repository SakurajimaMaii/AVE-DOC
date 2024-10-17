# 概览

[![JDK Version](https://img.shields.io/badge/jdk%20version-17-2300b894?style=flat)](https://img.shields.io/badge/jdk%20version-17-2300b894)
[![GitHub license](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg?style=flat)](https://www.apache.org/licenses/LICENSE-2.0)

!!! tip "依赖更新说明"

    从 **1.3.1** 版本开始，日志核心库将作为独立的模块进行发布。

## 特性

```kotlin
val logFactory: LogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    install(LogPrinter)
}

val logcat = logFactory("global")
logcat.d("这是一条日志")
```

<div class="result" markdown>
- 支持插件化安装。
- 支持自定义日志打印格式。
- 支持显示日志位置用于快速定位。
- 支持显示当前打印的日志信息。
- 支持日志文件存储。
- 支持对象以 json(pretty 可选) 风格输出。
- 支持 JsonString 打印。
</div>

## 日志风格

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-core/#134)

通过 [LogFormat](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-log-format/index.html) 可以自定义日志风格，例如为 [Logger.desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 指定风格为 [LineColorfulFormat](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop.format/-line-colorful-format/index.html) 。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter) {
        logger = Logger.desktop(LineColorfulFormat)
    }
}
```

<div class="result" markdown>

=== "表格风格(TableFormat)"
    
    <figure markdown="span">
    ![table_format](../img/table_format.png)
    </figure>

=== "线性风格(LineFormat)"

    <figure markdown="span">
    ![log_desktop](../img/line_format.png)
    </figure>

=== "多彩线性风格(LineColorfulFormat)"

    <figure markdown="span">
    ![log_desktop](../img/line_colorful_format.png)
    </figure>

=== "简约模式(OnlyMsgFormat)"

    <figure markdown="span">
    ![log_desktop](../img/only_msg_format.png)
    </figure>

</div>

## 面向 Tencent/Mars

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

通过 [Logger.mars()](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 将 [Tencent/Mars](https://github.com/Tencent/mars) 的 **xlog** 组件快速集成： 

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogPrinter) {
        logger = Logger.mars(logDir, logCache)
    }
}
```

## 面向 Okhttp

[:octicons-tag-24: Version 1.3.3](https://ave.entropy2020.cn/version/log-okhttp/#133)

```kotlin
// Add Interceptor 
val logcat = logFactory("global") 
val okhttp = OkHttpClient
    .Builder()
    .addInterceptor(Okhttp3Interceptor(logcat))     
    .build()  
    
// Make a request 
val request: Request = Request.Builder()
    .url("http://127.0.0.1:7777")
    .build()
okhttp.newCall(request).execute()
```
<div class="result" markdown>

![log_okhttp](../img/okhttp.png){ align=right width="500" }

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

### log-slf4j

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-slf4j)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-slf4j:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-slf4j:$version")
    ```
