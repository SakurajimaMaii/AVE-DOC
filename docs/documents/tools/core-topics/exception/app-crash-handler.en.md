# App default uncaught exception handler

[:octicons-tag-24: Version 1.5.1](https://ave.entropy2020.cn/version/tools/#151)

[AppCrashHandler](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.exception/-app-crash-handler/index.html) is used to set the default handler invoked when a thread abruptly terminates due to an uncaught exception, and no other handler has been defined for that thread.

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
