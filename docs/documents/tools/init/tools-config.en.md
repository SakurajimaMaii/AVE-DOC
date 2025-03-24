# Initialization

!!! warning "Deprecated"

    Starting from version [1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#111) you don't need to initialize VastTools manually.

```kotlin
class App: Application() {

    override fun onCreate() {
        super.onCreate()
        ToolsConfig.init(this)
    }

}
```
