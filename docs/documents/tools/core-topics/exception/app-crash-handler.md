# 全局异常处理

[:octicons-tag-24: Version 1.5.1](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#151)

[AppCrashHandler](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.exception/-app-crash-handler/index.html) 可以设置当线程由于未捕获的异常而突然终止并且尚未为该线程定义其他处理程序时调用的默认处理程序。

```kotlin
class App : Application() {

    override fun onCreate() {
        super.onCreate()
        setDefaultUncaughtExceptionHandler { t, e, stackTraceInfo ->
            ...
        }
    }

}
```
