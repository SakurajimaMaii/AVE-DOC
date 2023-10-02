# Usage

## Level

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Logging currently provides the following levels.

|  Level  |    Attributes    |
| :-----: | :--------------: |
| VERBOSE | LogLevel.VERBOSE |
|  DEBUG  |  LogLevel.DEBUG  |
|  INFO   |  LogLevel.INFO   |
|  WARN   |  LogLevel.WARN   |
|  ERROR  |  LogLevel.ERROR  |

For example, you can call the `i()` method to print **INFO** level logs.

## Log factory

### Switch

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

By configure `LogSwitch` , you can open or close the log.

```kotlin
val mLogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    .... 
}
```

!!! note "Conditions for log printing"

    Logs will be printed only if the application is in debug mode and the logging system is enabled.

### Format

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Configure the log format by configuring the `LogFormat` plugin.

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

#### Char length of the single log

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Set `singleLogCharLength` in the configuration to 30, that is, each line of logs can print up to 30 characters.

!!! notes "Character Description"

     Each character is calculated according to UTF-8 maximum 4Bytes.

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

#### Limit the maximum number of prints

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Set `maxPrintTimes` to 1 in the configuration, that is, a maximum of 1 line will be printed in the extremely long log.

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

### Json converter

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

Currently the following three Json converters are provided:

|       类名        |                          属性                           |
| :---------------: | :-----------------------------------------------------: |
| FastJsonConverter | Base on [FastJson](https://github.com/alibaba/fastjson) |
|   GsonConverter   |     Base on [Gson](https://github.com/google/gson)      |
| JacksonConverter  | Base on [Jackson](https://github.com/FasterXML/jackson) |

```kotlin
val mLogFactory = getLogFactory {
    install(LogJson) {
        converter = GsonConverter(true)
        ...
    }
    ... 
}
```

### Storage

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

The `LogStorage` plugin allows you to store the logs into files. The configuration is as follows:

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

[Sample file](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/log/AVE_1694179554073.log){ .md-button }
