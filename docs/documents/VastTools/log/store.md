# 日志存储

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/VastTools/#131)

如果想要启用存储功能，你需要配置 [LogStorage](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-storage/index.html?query=class%20LogStorage(val%20mConfiguration:%20LogStorage.Configuration)) 插件，并调用 [android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 来获取 [AndroidStore](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/-android-store/index.html) 。

```kotlin
val mLogFactory: LogFactory = getLogFactory {
    ...
    install(LogStorage) {
        logStore = LogStore.android()
    }
}
```

以下是按照默认配置存储的日志格式：

```xml
2024-05-19 20:54:58 INFO [main] FileActivity  (FileActivity.kt:44) 苏州园林里都有假山和池沼。假山的堆叠，可以说是一项艺术而不仅是技术。或者是重峦叠嶂，或者是几座小山配合着竹子花木，全在乎设计者和匠师们生平多阅历，胸中有邱壑，才能使游览者攀登的时候忘却苏州城市，只觉得身在山间。至于池沼，大多引用活水。有些园林池沼宽敞，就把池沼作为全园的中心，其他景物配合着布置。水面假如成河道模样，往往安排桥梁。假如安排两座以上的桥梁，那就一座一个样，决不雷同。池沼或河道的边沿很少砌齐整的石岸，总是高低屈曲任其自然。还在那儿布置几块玲珑的石头，或者种些花草：这也是为了取得从各个角度看都成一幅画的效果。池沼里养着金鱼或各色鲤鱼，夏秋季节荷花或睡莲开放，游览者看“鱼戏莲叶间”，又是入画的一景。 
2024-05-19 20:54:58 DEBUG [main] FileActivity  (FileActivity.kt:45) 这是一条日志
2024-05-19 20:54:58 WARN [main] FileActivity  (FileActivity.kt:46) {"password":"123456789","username":"小明"}
```

[查看示例文件](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/log/AVE_2024_05_19_21_57_27.log){ .md-button }

## 日志文件存储位置

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/VastTools/#131)

[android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 提供了 `fileRoot` 参数来设置日志文件存储位置。

!!! note "默认文件存储位置"

    data/data/packagename/files/log

## 日志文件名

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/VastTools/#131)

[android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 提供了 `fileNamePrefix` 和 `fileNameDateSuffixSdf` 参数来设置日志文件名的前缀和后缀的日期格式。

!!! note "默认文件名"

    ${AppName}_2024_05_19_21_57_27


## 日志文件大小

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/VastTools/#131)

[android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 提供了 `fileMaxSize` 参数来设置单个日志文件的大小，以字节为单位。

## 日志存储格式

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/VastTools/#131)

[android()](https://api.ave.entropy2020.cn/tools/com.ave.vastgui.tools.log/android.html) 提供了 `storageFormat` 参数来设置日志在文件中的存储格式，以下是函数提供的默认值：

```kotlin
@JvmOverloads
fun LogStore.Companion.android(
    ...
    storageFormat: (LogInfo) -> String = { info ->
        """
        ${timeSdf.format(info.mTime)} ${info.mLevel} [${info.mThreadName}] ${info.mTag} 
         (${info.mStackTrace?.fileName}:${info.mStackTrace?.lineNumber}) ${info.mContent}
        """.trimIndent().replace("\n", "")
    }
): AndroidStore
```

对应的存储效果如下所示：

```xml
2024-05-19 20:54:58 DEBUG [main] FileActivity  (FileActivity.kt:45) 这是一条日志
```
