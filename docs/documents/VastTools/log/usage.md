# 使用

## 日志级别

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

[LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) 目前支持以下级别。

|  级别   |       属性       |
| :-----: | :--------------: |
| VERBOSE | LogLevel.VERBOSE |
|  DEBUG  |  LogLevel.DEBUG  |
|  INFO   |  LogLevel.INFO   |
|  WARN   |  LogLevel.WARN   |
|  ERROR  |  LogLevel.ERROR  |

例如，你可以调用 `i()` 方法来打印 **INFO** 级别的日志。

## 日志工厂

### 日志开关

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

[LogSwitch](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log.plugin/-log-switch/index.html) 提供了 `open` 参数

```kotlin
val mLogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    .... 
}
```

!!! note "日志打印的条件"

    只有应用处于调试模式且开启了日志系统才会打印日志。

### 日志格式化

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

我们以下面的一段话为示例日志内容：

> 安卓（Android）是一种基于Linux内核（不包含GNU组件）的自由及开放源代码的移动操作系统。主要应用于移动设备，如智能手机和平板电脑，由美国Google公司和开放手机联盟领导及开发。

```xml
21:28:41.093 LogActivity D  ╔═══════════════════════════════════════════════════════════════════════════════════════════════
21:28:41.093 LogActivity D  ║ Thread: main
21:28:41.093 LogActivity D  ╟───────────────────────────────────────────────────────────────────────────────────────────────
21:28:41.093 LogActivity D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
21:28:41.093 LogActivity D  ╟───────────────────────────────────────────────────────────────────────────────────────────────
21:28:41.093 LogActivity D  ║ 安卓（Android）是一种基于Linux内核（不包含GNU组件）的自由及开放源代码的移动操作系统。主要应用于移动设备，如智能手机和平板电脑，由美国Google公司和开放手机联盟领导及开发。
21:28:41.093 LogActivity D  ╚═══════════════════════════════════════════════════════════════════════════════════════════════
```

#### 限制每行字符数

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

`maxSingleLogLength` 用于设置单行日志的最大打印长度，每个字符按照 UTF-8 最大 4Bytes 计算。因此实际打印结果可能会略微有差异，这是正常的。

```kotlin
val mLogFactory = getLogFactory {
    install(LogPrinter) {
        maxSingleLogLength = 30
    }
    ... 
}
```

```xml
21:32:15.131 LogActivity D  ╔════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
21:32:15.131 LogActivity D  ║ Thread: main
21:32:15.131 LogActivity D  ╟────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
21:32:15.131 LogActivity D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
21:32:15.131 LogActivity D  ╟────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
21:32:15.132 LogActivity D  ║ 安卓（Android）是一种基于Linux内核（不包含GNU组件）的自由及开放源代码的移动操作系统
21:32:15.132 LogActivity D  ║ 。主要应用于移动设备，如智能手机和平板电脑，由美国Google公司和开放手机联盟领导及
21:32:15.132 LogActivity D  ║ 开发。
21:32:15.132 LogActivity D  ╚════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
```

#### 限制最多打印次数

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

`maxPrintTimes` 用于设置日志打印的重复次数，例如根据设置超长的日志被分割为 10 行，如果 `maxPrintTimes` 被设置为 5 ，则只会打印前五行内容。

```kotlin
val mLogFactory = getLogFactory {
    install(LogPrinter) {
        maxSingleLogLength = 100
        maxPrintTimes = 5
    }
    ...
}
```

!!! warn "行数限制说明"

    Json 对象不收该项限制。

```xml
21:41:04.297 LogActivity D  ╔════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
21:41:04.298 LogActivity D  ║ Thread: main
21:41:04.298 LogActivity D  ╟────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
21:41:04.298 LogActivity D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
21:41:04.298 LogActivity D  ╟────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
21:41:04.298 LogActivity D  ║ 安卓（Android）是一种基于Linux内核（不包含GNU组件）的自由及开放源代码的移动操作系统
21:41:04.298 LogActivity D  ╚════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
```

### 日志 Json 转换器

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

目前提供了以下三种 Json 序列化对象

|  类名   |       属性       |
| :-----: | :--------------: |
| FastJsonConverter | 基于 [FastJson](https://github.com/alibaba/fastjson) 打造 |
|  GsonConverter  |  基于 [Gson](https://github.com/google/gson) 打造  |
|  JacksonConverter   |  基于 [Jackson](https://github.com/FasterXML/jackson) 打造   |

```kotlin
val mLogFactory = getLogFactory {
    install(LogJson){
        converter = GsonConverter(true)
    }
    ... 
}
```

### 日志存储

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

`LogStorage` 插件允许你将对应的日志存储进文件当中，配置如下：

```kotlin
val mLogFactory = getLogFactory {
    install(LogStorage) {
        fileMaxSize = 1024L * 1000
        storageFormat = { time, level, content ->
            "$level || $time || $content "
        }
        ...
    }
    ... 
}
```

[查看存储文件示例](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/log/AVE_1694179554073.log){ .md-button }
