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

### 日志存储


