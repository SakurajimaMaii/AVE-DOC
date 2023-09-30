# 初始化

你需要在 `Application` 内初始化 `VastTools` 。

```kotlin
class App: Application() {

    override fun onCreate() {
        super.onCreate()
        ToolsConfig.init(this)
    }

}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/App.kt){ .md-button }
