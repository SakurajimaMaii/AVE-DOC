# Description

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Here is a log example.

```xml
20:41:40.099 LogActivity  D  ╔═════════════════════════════════════════════════════════════════════════════
20:41:40.099 LogActivity  D  ║ Thread: main
20:41:40.099 LogActivity  D  ╟─────────────────────────────────────────────────────────────────────────────
20:41:40.099 LogActivity  D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
20:41:40.099 LogActivity  D  ╟─────────────────────────────────────────────────────────────────────────────
20:41:40.099 LogActivity  D  ║ This is a test log.
20:41:40.099 LogActivity  D  ╚═════════════════════════════════════════════════════════════════════════════
```

## Quick start

### Creating LogFactory

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

By calling [getLogFactory](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/get-log-factory.html?query=fun%20getLogFactory(factory:%20LogFactory.()%20-%3E%20Unit):%20LogFactory) ,you can get [LogFactory](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-factory/index.html) to configure the Log.

```kotlin
val mLogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    install(LogPrinter) {
        maxSingleLogLength = 50
        maxPrintTimes = 3
    }
    install(LogJson) {
        converter = GsonConverter(true
    }
}
```

### Print Log

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

You can create a [LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) by calling [getLog](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-factory/get-log.html?query=fun%20getLog(clazz:%20Class%3C*%3E):%20LogUtil) , which makes you to print log in terminal. 

```kotlin
private val logger = mLogFactory.getLog(this::class.java)

logger.d("This is a test log.")
```

### Json

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

By calling [json](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/json.html) of [LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) , you can print the log content in json format.

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
