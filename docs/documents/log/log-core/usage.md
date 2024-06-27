# 使用

## 日志级别

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

目前支持以下级别。

|         级别          |       属性       |
| :-------------------: | :--------------: |
|        VERBOSE        | LogLevel.VERBOSE |
|         DEBUG         |  LogLevel.DEBUG  |
|         INFO          |  LogLevel.INFO   |
|         WARN          |  LogLevel.WARN   |
|         ERROR         |  LogLevel.ERROR  |
| ASSERT // since 1.3.1 | LogLevel.ASSERT  |

例如，你可以调用 `i()` 方法来打印 **INFO** 级别的日志。

## 日志配置

日志配置通过 [getLogFactory](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/get-log-factory.html) 安装相关插件实现：

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    // 安装日志开关
    install(LogSwitch) {
        open = true
    }
    // 安装日志打印插件
    install(LogPrinter) {
        logger = Logger.android(maxPrintTimes = 5)
    }
    // 安装 Json 解析插件
    install(LogJson){
        converter = GsonConverter(true)
    }
}
```

### 日志打印

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

从 **1.3.1** 版本开始，日志的打印和开发场景相关：

- 面向 Android ：调用 [android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 获取 [AndroidLogger](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/-android-logger/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/VastTools/log/logger/) 。

- 面向 Kotlin/Java 应用 ： 调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 获取 [DesktopLogger](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-logger/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/log/log-desktop/logger/) 。

### 日志 Json 转换器

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

目前提供了以下三种 Json 序列化对象

|       类名        |                           属性                            |
| :---------------: | :-------------------------------------------------------: |
| FastJsonConverter | 基于 [FastJson](https://github.com/alibaba/fastjson) 打造 |
|   GsonConverter   |     基于 [Gson](https://github.com/google/gson) 打造      |
| JacksonConverter  | 基于 [Jackson](https://github.com/FasterXML/jackson) 打造 |

```kotlin
val mLogFactory = getLogFactory {
    install(LogJson){
        converter = GsonConverter(true)
    }
    ... 
}
```

### 日志存储

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

从 **1.3.1** 版本开始，日志的打印和开发场景相关：

- 面向 Android ：调用 [android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 获取 [AndroidStore](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/-android-store/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/VastTools/log/store/) 。

- 面向 Kotlin/Java 应用 ： 调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 获取 [DesktopLogger](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-logger/index.html) ，具体使用请参考 [链接](https://ave.entropy2020.cn/documents/log/log-desktop/store/) 。
