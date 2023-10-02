# Description

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

```xml
20:41:40.099 LogActivity  D  ╔═════════════════════════════════════════════════════════════════════════════
20:41:40.099 LogActivity  D  ║ Thread: main
20:41:40.099 LogActivity  D  ╟─────────────────────────────────────────────────────────────────────────────
20:41:40.099 LogActivity  D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
20:41:40.099 LogActivity  D  ╟─────────────────────────────────────────────────────────────────────────────
20:41:40.099 LogActivity  D  ║ 这是一条测试日志
20:41:40.099 LogActivity  D  ╚═════════════════════════════════════════════════════════════════════════════
```

## Usage

### Create LogFactory

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Using `getLogFactory` to configure the log.

```kotlin
val mLogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    install(LogFormat) {
        singleLogCharLength = 500
        maxPrintTimes = 3
        converter = GsonConverter(true)
    }
}
```

### Print Log

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

```kotlin
private val logger = mLogFactory.getLog(this::class.java)

logger.d("This is a test log.")
```

### Json

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

```kotlin
data class User(val name: String, val age: Int)

private val logger = mLogFactory.getLog(this::class.java)
logger.json(LogLevel.DEBUG, User("Li Ming", 18))
```

```xml
21:52:29.843 LogActivity D  ╔═════════════════════════════════════════════════════════════════════════════
21:52:29.843 LogActivity D  ║ Thread: main
21:52:29.843 LogActivity D  ╟─────────────────────────────────────────────────────────────────────────────
21:52:29.843 LogActivity D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:45)
21:52:29.843 LogActivity D  ╟─────────────────────────────────────────────────────────────────────────────
21:52:29.844 LogActivity D  ║ {
21:52:29.844 LogActivity D  ║   "age": 18,
21:52:29.844 LogActivity D  ║   "name": "张三"
21:52:29.844 LogActivity D  ║ }
21:52:29.844 LogActivity D  ╚═════════════════════════════════════════════════════════════════════════════
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/java/com/ave/vastgui/app/activity/log){ .md-button }
