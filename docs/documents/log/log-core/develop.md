# 自定义

## 自定义 Logger 

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

通过实现 [Logger](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-logger/index.html?query=interface%20Logger) 接口并重写 [log](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-logger/log.html) 方法来使用自定义 `Logger` 。

```kotlin
// SimpleLogger.kt
class SimpleLogger : Logger {
    override fun log(info: LogInfo) {
        println(info.toString())
    }
}

// Logger.kt
val logFactory: LogFactory = getLogFactory {
    install(LogSwitch) {
        open = true
    }
    install(LogPrinter) {
        logger = SimpleLogger()
    }
}
```

[查看完整代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/libraries/log/core/src/test/kotlin/com/log/vastgui/core){ .md-button }

## 自定义 LogStore

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

通过实现 [LogStore](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-log-store/index.html?query=interface%20LogStore) 接口并重写 [store](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-log-store/store.html) 方法来使用自定义 `Logger` 。

例如框架本身就提供了 [DesktopStore](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-store/index.html) 和 [AndroidStore](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/-android-store/index.html) 两种实现，你可以将其作为参考。

[DesktopStore](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/log/desktop/src/main/kotlin/com/log/vastgui/desktop/DesktopStore.kt){ .md-button } [AndroidStore](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/kotlin/com/ave/vastgui/tools/log/AndroidStore.kt){ .md-button }

## 自定义 Json 转换器

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

通过实现 [Converter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.json/-converter/index.html?query=interface%20Converter) 接口并重写方法来使用自定义 `Converter` 。

例如框架本身就提供了 [FastJsonConverter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.json/-fast-json-converter/index.html?query=class%20FastJsonConverter(val%20isPretty:%20Boolean)%20:%20Converter) 、 [GsonConverter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.json/-gson-converter/index.html) 和 [JacksonConverter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.json/-jackson-converter/index.html) 三种实现，你可以将其作为参考。

[FastJsonConverter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/log/core/src/main/kotlin/com/log/vastgui/core/json/FastJsonConverter.kt){ .md-button } [GsonConverter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/log/core/src/main/kotlin/com/log/vastgui/core/json/GsonConverter.kt){ .md-button } [JacksonConverter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/log/core/src/main/kotlin/com/log/vastgui/core/json/JacksonConverter.kt){ .md-button }
