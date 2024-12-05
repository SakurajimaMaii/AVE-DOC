# log-core

!!! tip 

    - 🥳🥳🥳 为推荐版本。
    - 删除线表示该版本存在错误，具体错误为描述中被删除线注解的部分。

## 1.3.11(Latest)

- 修复：

    - 修复日志处理流程错误导致无法正常打印的问题。 [**#ddbe988**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/ddbe9888e4227bf3d67c6d210756a326cfc01a16)

## 1.3.10

- 修复：

    - 修复 [LogTypeValidator](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-type-validator/index.html?query=class%20LogTypeValidator) 存在的问题。 [**#e18f68d**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/e18f68d8c6f1457e50a62b2473ef0d1b1766e22c)

## 1.3.9

- 修复：

    - 修复 [TableFormat](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.format/-table-format/index.html?query=class%20TableFormat(val%20mMaxSingleLogLength:%20Int,%20val%20mMaxPrintTimes:%20Int,%20val%20mHeader:%20TableFormat.LogHeader)%20:%20LogFormat) 换行存在的问题。 [**#0cd5459**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/0cd54593e5416a32ad3fa506725ebdcc8988c113)

## 1.3.8

- 新增：

    - 新增 [Log](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-tag/index.html) 用来作为日志的 tag 。

        ```kotlin
        logcat.i(LogTag(TAG)) { HELLO_WORLD }
        ```

        !!! example "实验性说明"

            [Log](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-tag/index.html) 和 [LogTag](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.base/-log-tag/index.htmll) 目前还处于实验性阶段。

- 更新：

    - 移除对 [Gson](https://github.com/google/gson) 和 [Jackson](https://github.com/FasterXML/jackson-databind) 的默认依赖。
    - 更改 [LogSwitch](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-switch/index.html?query=class%20LogSwitch(val%20open:%20Boolean)) 行为，用户只有安装该插件才能启用日志

- 修复：

    - 修复在 json 转换中将字符串 "null 123456" 被识别成 null 并打印 "null" 的问题。 [**#0cd5459**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/0cd54593e5416a32ad3fa506725ebdcc8988c113)

## 1.3.7

- 修复：

    - 修复 [logPipeline](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-cat/log-pipeline.html) 被错误添加 internal 修饰符的问题。 [**#cc3eb84**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/cc3eb844ba2a8166de5bf14894acaece2e4dafb4)

## ~~1.3.6~~

- 修复：

    - ~~修复 [logPipeline](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core/-log-cat/log-pipeline.html) 可见性错误~~，修复默认 tag 在添加 [@LogAPI](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.annotation/-log-api/index.html?query=internal%20annotation%20class%20LogApi) 可以再次修改的问题。 [**#0c70ede**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/0c70ede2b9a4d1c8de7d20e720316470cb716438)

- 过时：

    - 为了避免用户误解，将 getLogCat(clazz: Class<\*>) 和 invoke(clazz: Class<\*>) 设置为过时。 [**#031e699**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/031e69950e759e6b786282e7f2c8448a3fc7805a)

## 1.3.5

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
