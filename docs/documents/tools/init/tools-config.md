# 初始化

!!! warning "过时说明"

    从 [1.1.1](https://ave.entropy2020.cn/version/tools/#111) 版本开始你不需要手动初始化。

你需要在 `Application` 内初始化 `VastTools` 。

```kotlin
class App: Application() {

    override fun onCreate() {
        super.onCreate()
        ToolsConfig.init(this)
    }

}
```
