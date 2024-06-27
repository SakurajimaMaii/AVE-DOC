# 概述

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

!!! note "Tencent/Mars"

    [Tencent/Mars](https://github.com/Tencent/mars) 是微信官方的跨平台跨业务的终端基础组件。其中 xlog 是高可靠性高性能的运行期日志组件。

基于 [Tencent/Mars](https://github.com/Tencent/mars) 的 xlog 改造。集成了日志的打印和存储。指定 [LogPrinter](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-printer/index.html?query=class%20LogPrinter(val%20mConfiguration:%20LogPrinter.Configuration)) 的 `logger` 为 [MarsLogger](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/index.html) 即可启用：

```kotlin
// 指定日志的存储位置
val logDir = File(FileMgr.appInternalFilesDir(), "log")
val logCache = File(FileMgr.appInternalFilesDir(), "log-cache")

val mLogFactory: LogFactory = getLogFactory {
    // 配置插件
    install(LogPrinter) {
        logger = Logger.mars(logDir, logCache)
    }
}
```

### 文件写入模式

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `mode` 用于设置文件写入模式。分为异步和同步，变量定义参考 [MarsWriteMode](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars.base/-mars-write-mode/index.html) ， Release版本一定要用 [Async](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars.base/-mars-write-mode/-async/index.html) ， Debug 版本两个都可以，但是使用 [Sync](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars.base/-mars-write-mode/-sync/index.html) 可能会有卡顿。

### 文件存储位置

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

### 文件名前缀

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `namePreFix` 用于设置日志文件名的前缀，例如该值为 TEST ，生成的文件名为：TEST_20170102.xlog。

### 单一文件保存

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `singleLogFileEveryday` 用于设置是否将每天的日志保存在单独的一个文件当中。

### 单个文件最大大小

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `singleLogFileMaxSize` 用于设置单个文件的最大大小。

!!! warning "注意事项"

    当 `singleLogFileEveryday` 指定为 `false` 时该配置会生效。
