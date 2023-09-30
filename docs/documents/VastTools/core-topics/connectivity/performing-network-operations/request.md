# Request

`Request` 基于 `Call` 封装并进行了拓展。

!!! tip "迁移到 Request2"

    `Request` 最初是为了兼容 java 和 kotlin 混编的项目，并为你提供了基于 `ResponseStateListener` 和 `ResponseMutableLiveData` 的方法实现，但是因为 `Request` 需要数据实现 `ResponseApi` 接口，这在某些场景下是不便的，因此在 [0.5.1](https://ave.entropy2020.cn/version/VastTools/#051) 版本推出了 `Request2` ， `Request2` 不需要你实现 `ResponseApi` 接口。因此如果你的项目使用 kotlin ，那么强烈推荐你使用 `Request2` 。

!!! note "关于测试接口说明"

    感谢 [开放API-2.0](https://api.apiopen.top/) 提供的开源免费接口

## 快速开始

- 定义数据类型，实现 ResponseApi 接口

    ```kotlin
    data class RequestResponse(val code: Int, val message: String, val result: Result) : ResponseApi {
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

        override fun isSuccessful() = code == 200
        
        override fun code() = code
        
        override fun message() = message
    }
    ```

- 创建网络请求的接口

    ```kotlin
    interface RequestService {
        /**
         * [获取好看视频](https://api.apiopen.top/swagger/index.html#/%E5%BC%80%E6%94%BE%E6%8E%A5%E5%8F%A3/get_api_getHaoKanVideo)
         */
        @GET("/api/getHaoKanVideo")
        fun getHaoKanVideo(@Query("page") page: Int, @Query("size") size: Int): Request<RequestResponse>
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

    如果你不想使用 `RequestBuilder` ，你需要为 `Retrofit.Builder` 添加 `RequestAdapterFactory()` 以便数据能够正确解析。

    ```kotlin
    yourRetrofitBuilder.addCallAdapterFactory(RequestAdapterFactory())
    ```

- 监听网络请求结果

    ```kotlin
    NetRequestBuilder().create(RequestService::class.java)
        .getHaoKanVideo(page = 0, size = 2).request {
            onSuccess = { text = it.result.list[0].title }

            onError = { text = "遇到异常 ${it?.message}" }

            onFailed = { code, message -> text = "请求失败 $code $message" }
        }
    ```

## 配合 ResponseLiveData 使用

- 创建 ResponseLiveData 对象

    ```kotlin
    private val _requestResponse = ResponseMutableLiveData<RequestResponse>()
    val requestResponse: ResponseLiveData<RequestResponse>
        get() = _requestResponse
    ```

- 手动设置状态

    > 具体使用可以参考 [更新 ResponseLiveData 对象](https://ave.entropy2020.cn/documents/VastTools/core-topics/connectivity/performing-network-operations/ResponseLiveData/#responselivedata_4)

    我们在获取到请求成功的结果后，使用 `postValueAndSuccess` 方法手动的改变状态。

    ```kotlin
    fun getRequestResponse_2(page: Int, size: Int) {
        NetRequestBuilder().create(RequestService::class.java)
            .getHaoKanVideo(page = page, size = size)
            .request {
                onSuccess = {
                    _requestResponse.postValueAndSuccess(it)
                }
                onFailed = { errorCode, errorMsg ->
                    _requestResponse.postFailed(errorCode, errorMsg)
                }
                onError = {
                    _requestResponse.postError(it)
                }
            }
    }
    ```

- 自动设置状态

    将 `_requestResponse` 作为 `request` 的参数，该方法目前会监听以下状态 `Error` `Empty` `Success` `Failed` 。

    ```kotlin
    fun getRequestResponse_1(page: Int, size: Int) {
        NetRequestBuilder().create(RequestService::class.java)
            .getHaoKanVideo(page = page, size = size)
            .request(_requestResponse)
    }
    ```

- 监听StateLiveData的状态

    > 具体使用参考 [观察状态发生变化](https://ave.entropy2020.cn/documents/VastTools/core-topics/connectivity/performing-network-operations/ResponseLiveData/#_3)

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/net/Request.kt){ .md-button }
