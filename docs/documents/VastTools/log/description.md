# 简介

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

这是一条日志示例。

```xml
20:41:40.099 LogActivity  D  ╔═════════════════════════════════════════════════════════════════════════════
20:41:40.099 LogActivity  D  ║ Thread: main
20:41:40.099 LogActivity  D  ╟─────────────────────────────────────────────────────────────────────────────
20:41:40.099 LogActivity  D  ║ com.ave.vastgui.app.activity.LogActivity$onCreate$2.invoke(LogActivity.kt:44)
20:41:40.099 LogActivity  D  ╟─────────────────────────────────────────────────────────────────────────────
20:41:40.099 LogActivity  D  ║ 这是一条测试日志
20:41:40.099 LogActivity  D  ╚═════════════════════════════════════════════════════════════════════════════
```

## 快速开始

### 创建 LogFactory

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

通过 [getLogFactory](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/get-log-factory.html?query=fun%20getLogFactory(factory:%20LogFactory.()%20-%3E%20Unit):%20LogFactory) 可以获取 [LogFactory](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-factory/index.html) ，以便对日志进行配置。

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

### 打印日志

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

调用 [getLog](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-factory/get-log.html?query=fun%20getLog(clazz:%20Class%3C*%3E):%20LogUtil) 来获取 [LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) 对象，通过该对象打印日志。

```kotlin
private val logger = mLogFactory.getLog(this::class.java)

logger.d("这是一条测试日志")
```

### 打印 Json

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

[LogUtil](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/index.html) 提供了 [json](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.log/-log-util/json.html) 方法以便你将指定内容按照 Json 的格式打印出来。

```kotlin
// User 定义
data class User(val name: String, val age: Int)

// 在 Activity 中使用
private val logger = mLogFactory.getLog(this::class.java)
logger.json(LogLevel.DEBUG, User("张三", 18))
```

打印效果如下：

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

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/java/com/ave/vastgui/app/activity/log){ .md-button }
