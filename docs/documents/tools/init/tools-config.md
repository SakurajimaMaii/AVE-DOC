# 配置 VastTools

!!! warning "过时说明"

    从 [1.1.1](https://ave.entropy2020.cn/version/tools/#111) 版本开始你不需要手动初始化。

```kotlin
class App: Application() {

    override fun onCreate() {
        super.onCreate()
        ToolsConfig.init(this)
    }

}
```
