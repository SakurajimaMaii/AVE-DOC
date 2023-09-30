# 使用

## 日志级别

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

日志当前提供了以下级别。


|  级别   |       属性       |
| :-----: | :--------------: |
| VERBOSE | LogLevel.VERBOSE |
|  DEBUG  |  LogLevel.DEBUG  |
|  INFO   |  LogLevel.INFO   |
|  WARN   |  LogLevel.WARN   |
|  ERROR  |  LogLevel.ERROR  |

例如，你可以调用 `i()` 方法来打印 **INFO** 级别的日志。

## 日志工厂

日志工厂用来安装日志插件，目前提供了以下插件：

- LogSwitch: 用来控制日志的开启和关闭
- LogFormat: 用来控制日志的格式化

### 日志开关

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

通过配置 `LogSwitch` 插件来开启日志。

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

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

通过配置 `LogFormat` 插件来配置日志的格式。

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

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

在配置项中设置 `singleLogCharLength` 为 30 ，即每行日志最多打印 30 个字符。

!!! notes "字符说明"

    每个字符按照 UTF-8 最大 4Bytes 计算。

```kotlin
val mLogFactory = getLogFactory {
    install(LogFormat) {
        singleLogCharLength = 30
        ...
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

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

在配置项中设置 `maxPrintTimes` 为 1 ，即超长日志最多打印 1 行。

```kotlin
val mLogFactory = getLogFactory {
    install(LogFormat) {
        singleLogCharLength = 30
        maxPrintTimes = 1
        ...
    }
    ...
}
```

```xml
21:41:04.297 LogActivity D  ╔════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
21:41:04.298 LogActivity D  ║ Thread: main
21:41:04.298 LogActivity D  ╟────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
21:41:04.298 LogActivity D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
21:41:04.298 LogActivity D  ╟────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
21:41:04.298 LogActivity D  ║ 安卓（Android）是一种基于Linux内核（不包含GNU组件）的自由及开放源代码的移动操作系统
21:41:04.298 LogActivity D  ╚════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
```

!!! warn "行数限制说明"

    Json 对象不收该项限制。

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
    install(LogJson) {
        converter = GsonConverter(true)
        ...
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

[查看存储文件示例](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/log/AVE_1694179554073.log){ .md-button }
