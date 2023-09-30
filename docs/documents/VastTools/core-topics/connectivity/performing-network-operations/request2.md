# Request2

`Request2` 配合 Kotlin 的 [协程](https://kotlinlang.org/docs/coroutines-overview.html) 和 [Flow](https://kotlinlang.org/docs/flow.html) 能够简化网络请求流程。

!!! note "关于测试接口说明"

    感谢 [开放API-2.0](https://api.apiopen.top/) 提供的开源免费接口

## 快速开始

- 定义数据类型

    ```kotlin
    data class RequestResponse(val code: Int, val message: String, val result: Result) {
        data class Result(val list: List<Data>, val total: Int) {
            data class Data(
                val coverUrl: String, 
                val duration: String, 
                val id: Int, 
                val playUrl: String,
                val title: String,
                val userName: String,
                val userPic: String
            )
        }
    }
    ```

- 创建网络请求的接口

    ```kotlin
    private interface Request2Service {
        /**
         * [获取好看视频](https://api.apiopen.top/swagger/index.html#/%E5%BC%80%E6%94%BE%E6%8E%A5%E5%8F%A3/get_api_getHaoKanVideo)
         */
        @GET("/api/getHaoKanVideo")
        suspend fun getHaoKanVideo(@Query("page") page: Int, @Query("size") size: Int): Request2<Request2Response>
    }
    ```

- 使用 `RequestBuilder` 创建实例

    ```kotlin
    class NetRequestBuilder : RequestBuilder("https://api.apiopen.top") {

        override fun retrofitConfiguration(builder: Retrofit.Builder) {
            super.retrofitConfiguration(builder)
            builder.apply {
                addConverterFactory(GsonConverterFactory.create())
            }
        }

    }
    ```

    如果你不想使用 `RequestBuilder` ，你需要为 `Retrofit.Builder` 添加 `Request2AdapterFactory()` 以便数据能够正确解析。

    ```kotlin
    yourRetrofitBuilder.addCallAdapterFactory(Request2AdapterFactory())
    ```

    通过 `RequestBuilder.getApi` 方法你可以获取对应的 `flow` ，你可以对此进行收集和处理。

- 监听网络请求结果

    ```kotlin
    NetRequestBuilder()
        .getApi(Request2Service::class.java) {
            getHaoKanVideo(page = 0, size = 2)
        }.collect {
            text = when (it) {
                is Request2.Success -> it.data.result.list.get(0).title
                is Request2.Empty -> "这是一条空数据"
                is Request2.Exception -> "遇到异常 ${it.exception}"
                is Request2.Failure -> "${it.code} ${it.message}"
                else -> ""
            }
        }
    ```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/net/Request2.kt){ .md-button }
