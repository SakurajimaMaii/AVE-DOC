# log-core

!!! tip 

    🥳🥳🥳 为推荐版本。

## 1.3.5(Latest)

- 更新：

    - 用户无需调用 [getLogCat()](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-factory/get-log-cat.html) 来获取 [LogCat](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-cat/index.html) 对象。 [**#9b85f6e**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/9b85f6e6b302f5bf1c36d02a57b3d09453ed2001)
        
        ```kotlin
        val logcat = logFactory("global")
        ```

    - i 等日志方法新增对于 Any? 对象的支持。 [**#9b85f6e**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/9b85f6e6b302f5bf1c36d02a57b3d09453ed2001)

        ```kotlin
        val key: String? = System.getenv()["Key"]
        logcat.d(key)
        ```

## 1.3.4 🥳🥳🥳

- 更新：

    - 日志框架使用 Pipeline 设计模式，极大的增加了拓展性。 [**#acb6f6b**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/acb6f6b14e39e8687b473a5e1943a993fda82581)
        
        !!! note "致谢"
        
            非常感谢 [ywnkm](https://github.com/ywnkm) 对于这一功能的支持。

- 新增：

    - [LogFormat](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-log-format/index.html) 用于用户自定义统一的日志模板。 [**#9fd98fd**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/9fd98fdee337e7b3511ede27b7ac483a87423ccc)

## 1.3.3

- 新增：

    - [LogUtil](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-util/index.html?query=class%20LogUtil) 新增 `logPrint(logInfo: LogInfo)` 方法。[**#3562aa9**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/3562aa925b940c147fbca7e70837c9a091eb1793)

- 更新：

    - [LogUtil](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-util/index.html?query=class%20LogUtil) 修改了 [mDefaultTag](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-util/m-default-tag.html) 和 [logPrint](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-util/log-print.html) 可见性。[**#3562aa9**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/3562aa925b940c147fbca7e70837c9a091eb1793)
    - [VastCore](https://central.sonatype.com/artifact/io.github.sakurajimamaii/VastCore/overview) 更新到 0.1.0 版本。

## 1.3.2

- 更新：

    - 更新了 [LogInfo](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-log-info/index.html?query=data%20class%20LogInfo%C2%A0constructor(val%20mCurrentThread:%20Thread,%20val%20mLevel:%20LogLevel,%20val%20mTag:%20String,%20val%20mTime:%20Long,%20val%20mContent:%20String,%20val%20mType:%20Int,%20val%20mThrowable:%20Throwable?%20=%20null)) 部分字段。

## 1.3.1

- 更新：

    - 日志作为独立模块使用。
