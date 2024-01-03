# Usage

## Level

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

[LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) currently supports the following levels.

|  Level  |   Implemention   |
| :-----: | :--------------: |
| VERBOSE | LogLevel.VERBOSE |
|  DEBUG  |  LogLevel.DEBUG  |
|  INFO   |  LogLevel.INFO   |
|  WARN   |  LogLevel.WARN   |
|  ERROR  |  LogLevel.ERROR  |

For example, you can call `i()` to print log message in **INFO** level.

## LogFactory

### LogSwitch

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

[LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) will print log when the app is in debug mode and the `open` of [LogSwitch](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log.plugin/-log-switch/index.html) is true.

```kotlin
val mLogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    .... 
}
```

### LogPrinter

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

Let’s take the following paragraph as an example log content:

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

#### maxSingleLogLength

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

`maxSingleLogLength` allows you to configure the max length of one line. Each character in line is calculated as 4 bytes([UTF-8](https://home.unicode.org/)). Therefore the actual printed results may vary slightly, this is normal.

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

#### maxPrintTimes

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

Set `maxPrintTimes` is the repeat number of prints. For example, the log content 
is divided into ten lines depending on maxSingleLogLength. If you set maxPrintTimes 
to 5, only the first five lines will be printed.

```kotlin
val mLogFactory = getLogFactory {
    install(LogPrinter) {
        maxSingleLogLength = 100
        maxPrintTimes = 5
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

### LogJson

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

Currently the following three Json converters are provided:

|       Class       |                          Base                           |
| :---------------: | :-----------------------------------------------------: |
| FastJsonConverter | Base on [FastJson](https://github.com/alibaba/fastjson) |
|   GsonConverter   |     Base on [Gson](https://github.com/google/gson)      |
| JacksonConverter  | Base on [Jackson](https://github.com/FasterXML/jackson) |

```kotlin
val mLogFactory = getLogFactory {
    install(LogJson){
        converter = GsonConverter(true)
    }
    ... 
}
```

### LogStorage

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

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

[Sample file](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/log/AVE_1694179554073.log){ .md-button }
