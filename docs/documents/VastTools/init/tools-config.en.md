# ToolsConfig

!!! warning "Deprecated"

    Starting from version [1.1.1](https://ave.entropy2020.cn/version/VastTools/#111) you don't need to initialize VastTools manually.

Call `ToolsConfig.init` to initialize tool configuration.

```kotlin
class App: Application() {

    override fun onCreate() {
        super.onCreate()
        ToolsConfig.init(this)
    }

}
```
