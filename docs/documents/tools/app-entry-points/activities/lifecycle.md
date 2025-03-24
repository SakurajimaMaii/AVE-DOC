# 生命周期

[:octicons-tag-24: Version 1.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#150)

可以通过 [ActivityLifecycleLogger](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.lifecycle/-activity-lifecycle-logger/index.html) 用来观察Activity生命周期。

```kotlin
val logger = ActivityLifecycleLogger(mLogFactory.getLogCat(this::class.java))
registerActivityLifecycleCallbacks(logger)
```