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

## 添加依赖

当前版本 ![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/log-mars)

=== "gradle"

    ```groovy
    implementation 'io.github.sakurajimamaii:log-mars:$version'
    ```

=== "kts"

    ```kotlin
    implementation("io.github.sakurajimamaii:log-mars:$version")
    ```

## 文件写入模式

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `mode` 用于设置文件写入模式。分为异步和同步，变量定义参考 [MarsWriteMode](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars.base/-mars-write-mode/index.html) ， Release版本一定要用 [Async](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars.base/-mars-write-mode/-async/index.html) ， Debug 版本两个都可以，但是使用 [Sync](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars.base/-mars-write-mode/-sync/index.html) 可能会有卡顿。

## 文件存储位置

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `logdir` 和 `cache` 用于设置日志文件存储位置。

## 文件名前缀

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `namePreFix` 用于设置日志文件名的前缀，例如该值为 TEST ，生成的文件名为：TEST_20170102.xlog。

## 单一文件保存

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `singleLogFileEveryday` 用于设置是否将每天的日志保存在单独的一个文件当中。

## 单个文件最大大小

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `singleLogFileMaxSize` 用于设置单个文件的最大大小。

!!! warning "注意事项"

    当 `singleLogFileEveryday` 指定为 `false` 时该配置会生效。

## 单个日志文件的存储时间

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `singleLogFileStoreTime` 用于设置单个文件的存储时间。

## 缓存时间

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

我们以上面设置的日志文件夹为例：

```kotlin
val logDir = File(FileMgr.appInternalFilesDir(), "log")
val logCache = File(FileMgr.appInternalFilesDir(), "log-cache")
```

正常情况下文件结构如下：

```
├─log-cache
│  └─ log.mmap3
└─ log
   ├─ log_20240620.xlog
   └─ log_20240621.xlog
```

如果设置了 `singleLogFileCacheDays` ，日志文件会先存储在 `log-cache` 目录下，`singleLogFileCacheDays` 天后移动到 `log` 文件夹下面。

```
├─log-cache
│  ├─ log.mmap3
│  ├─ log_20240620.xlog
│  └─ log_20240621.xlog
└─ log
```

## 加密秘钥

[:octicons-tag-24: Version 1.3.4](https://ave.entropy2020.cn/version/log-mars/#134)

[mars](https://api.ave.entropy2020.cn/log/mars/com.log.vastgui.mars/mars.html) 提供了 `pubKey` 用于设置日志文件的加密公钥。以下是相关流程：

- 点击 [gen_key.py](https://github.com/Tencent/mars/blob/2b0aa80ad83a50521bb651c8ca5dc6b25bd0125d/mars/xlog/crypt/gen_key.py) 下载脚本。
- 运行 gen_key.py 获取密钥对，将公钥设置为 `pubKey` 。

!!! note "使用提示"

    如果遭遇 ModuleNotFoundError: No module named 'pyelliptic' 异常，可以执行以下代码进行安装：

    ```
    pip install https://github.com/mfranciszkiewicz/pyelliptic/archive/1.5.10.tar.gz#egg=pyelliptic
    ```

    需要注意的是，需要安装 1.5.10 版本的 pyplliptic ，不能安装最新版本的，否则会报类似下面这个错误:

    ```
    Traceback (most recent call last):
    File "decode_mars_crypt_log_file.py", line 9, in <module>
        import pyelliptic
    File "C:\Developer\Python2.7.18\lib\site-packages\pyelliptic\__init__.py", line 43, in <module>
        from .openssl import OpenSSL
    File "C:\Developer\Python2.7.18\lib\site-packages\pyelliptic\openssl.py", line 309, in <module>
        raise Exception("Couldn't load OpenSSL lib ...")
    Exception: Couldn't load OpenSSL lib ...
    ```

- 点击 [compose-multiplatform-xlog-decode](https://github.com/leavesCZY/compose-multiplatform-xlog-decode/releases/tag/v1.0.0) 下载解密工具，选择对应的日志文件和私钥即可获取日志内容。
