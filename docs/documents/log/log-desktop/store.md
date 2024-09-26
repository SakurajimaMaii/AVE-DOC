# 日志存储

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-desktop/#131)

如果想要在 Kotlin/Java 应用中启用日志存储，需要配置 [LogStorage](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-storage/index.html?query=class%20LogStorage(val%20mConfiguration:%20LogStorage.Configuration)) 插件，并调用 [desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 来获取 [DesktopStore](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/-desktop-store/index.html) 。

```kotlin
val logFactory: LogFactory = getLogFactory {
    ...
    install(LogStorage) {
        logStore = LogStore.desktop("", 1024L * 1000)
    }
}
```

以下是按照默认配置存储的日志格式：

```xml
2024年5月19日 下午8:21:16 [VERBOSE|KotlinUnitTest|Test worker] (KotlinUnitTest.kt:48) {"employees":[{"firstName":"Bill","lastName":"Gates"},{"firstName":"George","lastName":"Bush"},{"firstName":"Thomas","lastName":"Carter"}]} 
2024年5月19日 下午8:21:16 [DEBUG|KotlinUnitTest|Test worker] (KotlinUnitTest.kt:50) {"name":"Xiao Ming","age":19} 
2024年5月19日 下午8:21:16 [INFO|KotlinUnitTest|Test worker] (KotlinUnitTest.kt:52) [1,2,3,4,5,6,7,8,9] 
2024年5月19日 下午8:21:16 [WARN|KotlinUnitTest|Test worker] (KotlinUnitTest.kt:53) This is a log. 
2024年5月19日 下午8:21:16 [ERROR|KotlinUnitTest|Test worker] (KotlinUnitTest.kt:54) This is a log. 
2024年5月19日 下午8:21:16 [ASSERT|KotlinUnitTest|Test worker] (KotlinUnitTest.kt:55) This is a log. 
```

[查看示例文件](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/libraries/log/desktop/log){ .md-button }

## 日志文件存储位置

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-desktop/#131)

[desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 提供了 `fileRoot` 参数来设置日志文件存储位置。

!!! note "默认文件存储位置"

    如果 `fileRoot` 为空字符串，会在当前文件夹下面创建一个名为 `log` 的文件夹用来存储日志文件。

## 日志文件大小

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-desktop/#131)

[desktop()](https://api.ave.entropy2020.cn/log/desktop/com.log.vastgui.desktop/desktop.html) 提供了 `fileMaxSize` 参数来设置单个日志文件的大小，以字节为单位。
