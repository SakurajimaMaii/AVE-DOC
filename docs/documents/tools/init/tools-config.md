# 配置 VastTools

!!! warning "过时说明"

    从 [1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#111) 版本开始你不需要手动初始化。

```kotlin
class App: Application() {

    override fun onCreate() {
        super.onCreate()
        ToolsConfig.init(this)
    }

}
```
