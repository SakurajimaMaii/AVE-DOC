# log-okhttp

!!! tip 

    🥳🥳🥳 为推荐版本。

## 1.3.9(Latest) 

- 新增：

    - 新增 SanitizedHeaders 功能。 [**#afdf8d1**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/afdf8d1035c605d2ddecfa0710fde11c2ea18128)

        ```kotlin
        Okhttp3Interceptor(logcat)
            .sanitizedHeaders("Authorization","***")
            .sanitizedHeaders("User-Agent","xxx")
        ```

        则上述的请求头内容会被替换成指定内容：

        ![Okhhtp sanitized headers](../img/okhttp_sanitized_headers.png)

## 1.3.6 

- 修复：

    - 修复请求头没有打印 [Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) 的问题。 [**#71431aa**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/71431aab1b11868d96a4b3d5f96abb63855311aa)

## 1.3.5 🥳🥳🥳

- 更新：

    - [Okhttp3Interceptor](https://api.ave.entropy2020.cn/log/okhttp/com.log.vastgui.okhttp/-okhttp3-interceptor/index.html) 允许创建多个实例。 [**#0884996**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/0884996ed51478846617819a63772bfee48541a1)
    - 新增对于 Server-Sent Events(**SSE**) 消息支持，以下为示例：![Okhhtp sse](../img/okhttp_sse.png) 点击 [示例](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/log/canary/libraries/log/okhttp/src/test/kotlin/SimpleTest.kt) 查看完整示例。

## 1.3.4

- 更新：

    - [log-core](https://central.sonatype.com/artifact/io.github.sakurajimamaii/log-core/overview) 更新到 1.3.4 版本。

## 1.3.3

- 更新：

    - 作为独立模块使用。