# 全局异常处理

[:octicons-tag-24: Version 1.4.1](https://ave.entropy2020.cn/version/tools/#141)

[AppCrashHandler](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.exception/-app-crash-handler/index.html) 允许你对于应用中未捕获的异常进行处理，避免应用意外崩溃，以下是使用示例：

```kotlin
// App.kt
// 配置日志打印，并在应用遭遇异常时启动 FileActivity
private val crashConfig =
    AppCrashHandler.Configuration(mLogFactory.getLog(App::class.java)) { _, _ ->
        val intent = Intent(ContextHelper.getAppContext(), FileActivity::class.java).apply {
            flags = Intent.FLAG_ACTIVITY_NEW_TASK
        }
        ContextHelper.getAppContext().startActivity(intent)
        exitProcess(0)
    }

class App : Application() {
    override fun onCreate() {
        super.onCreate()
        ...
        Thread.setDefaultUncaughtExceptionHandler(AppCrashHandler.getInstance(crashConfig))
    }
}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/net/OpenApi.kt){ .md-button }
