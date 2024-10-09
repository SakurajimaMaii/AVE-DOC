# 概述

[:octicons-tag-24: Version 1.3.7](https://ave.entropy2020.cn/version/log-slf4j/#137)

!!! example "实验性提示"

    针对 [SLF4J](https://www.slf4j.org/) 的支持目前处于开发阶段， API 随时可能发生变化。

```kotlin
@LogExperimental
class SLF4JKtTest {

    private var logger: Logger by Delegates.notNull()

    @Test
    fun simpleTest() {
        Slf4jProvider.Options.setFactory(logFactory)
        logger = LoggerFactory.getLogger("SLF4JKtTest")
        logger.debug("This is a message")
    }

}
```

## 添加依赖

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-slf4j)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-slf4j:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-slf4j:$version")
    ```

## 配置 

[:octicons-tag-24: Version 1.3.7](https://ave.entropy2020.cn/version/log-slf4j/#137)

通过 [Slf4jProvider.Options](https://api.ave.entropy2020.cn/log/slf4j/com.log.vastgui.slf4j/-slf4j-provider/-options/index.html) ，你可以进行相关配置，例如设置 [LogFactory](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-factory/index.html) ：

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
}

Slf4jProvider.Options.setFactory(logFactory)
```

!!! danger "提示"

    [Slf4jProvider.Options](https://api.ave.entropy2020.cn/log/slf4j/com.log.vastgui.slf4j/-slf4j-provider/-options/index.html) 的调用必须在 [LoggerFactory.getLogger](https://www.slf4j.org/api/org/slf4j/LoggerFactory.html#getLogger(java.lang.String)) 之前。
