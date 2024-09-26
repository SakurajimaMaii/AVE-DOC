# Request

`Request` 基于 `Call` 封装并进行了拓展。

!!! tip "迁移到 Request2"

    `Request` 最初是为了兼容 java 和 kotlin 混编的项目，并为你提供了基于 `ResponseStateListener` 和 `ResponseMutableLiveData` 的方法实现，但是因为 `Request` 需要数据实现 `ResponseApi` 接口，这在某些场景下是不便的，因此在 [0.5.1](https://ave.entropy2020.cn/version/tools/#051) 版本推出了 `Request2` ， `Request2` 不需要你实现 `ResponseApi` 接口。因此如果你的项目使用 kotlin ，那么强烈推荐你使用 `Request2` 。

!!! note "关于测试接口说明"

    感谢 [开放API-2.0](https://api.apiopen.top/) 提供的开源免费接口。

## 快速开始

- 定义数据类型，实现 [ResponseApi](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.network.response/-response-api/index.html) 接口。

    ```kotlin
    data class Sentences(
        val code: Int,
        val message: String,
        val result: Result
    ) : ResponseApi {
        data class Result(
            val from: String,
            val name: String
        )

        override fun isSuccessful(): Boolean = code == 200

        override fun message(): String = message
    }
    ```

- 创建网络请求的接口。

    ```kotlin
    interface OpenApiService {
        /**
         * 获取一句名言。
         */
        @GET("/api/sentences")
        fun sentences(): Request<Sentences>
    }
    ```

- 使用 [RequestBuilder](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.network.request/-request-builder/index.html) 创建实例。

    ```kotlin
    class OpenApi : RequestBuilder("https://api.apiopen.top") {
        override fun retrofitConfiguration(builder: Retrofit.Builder) {
            super.retrofitConfiguration(builder)
            builder.addConverterFactory(GsonConverterFactory.create())
        }
    }
    ```

    如果你不想使用 `RequestBuilder` ，你需要为 `Retrofit.Builder` 添加 [RequestAdapterFactory](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.network.request/-request-adapter-factory/index.html) 以便数据能够正确解析。

    ```kotlin
    yourRetrofitBuilder.addCallAdapterFactory(RequestAdapterFactory())
    ```

- 监听网络请求结果

    ```kotlin
    OpenApi().create(OpenApiService::class.java)
        .sentences()
        .request {
            onSuccess = { ... // 请求成功时 }
            onError = { ... // 请求遇错误时 }
            onFailed = { ... // 请求失败时 }
        }
    ```

## 配合 ResponseLiveData 使用

- 创建 [ResponseLiveData](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.network.response/-response-mutable-live-data/index.html) 对象。

    ```kotlin
    private val _sentence = ResponseMutableLiveData<Sentences>()
    val sentence: ResponseLiveData<Sentences>
        get() = _sentence
    ```

- 手动设置状态

    在获取到请求成功的结果后，使用 `postValueAndSuccess` 方法手动的改变状态。更多使用方法可以参考[更新 ResponseLiveData 对象](https://ave.entropy2020.cn/documents/VastTools/core-topics/connectivity/performing-network-operations/response-livedata/#responselivedata_4)。

    ```kotlin
    OpenApi().create(OpenApiService::class.java)
        .sentences()
        .request {
            onSuccess = { _sentence.postValueAndSuccess(it) }
            onError = { _sentence.postError(it) }
            onFailed = { code, message -> _sentence.postFailed(code, message) }
        }
    ```

- 自动设置状态

    将 `_sentence` 作为 `request` 的参数，该方法目前会监听以下状态 `Error` `Empty` `Success` `Failed` 。

    ```kotlin
    OpenApi().create(OpenApiService::class.java)
        .sentences()
        .request(_sentence)
    ```

- 监听 `ResponseLiveData` 的状态

    具体使用参考[观察状态发生变化](https://ave.entropy2020.cn/documents/VastTools/core-topics/connectivity/performing-network-operations/response-livedata/#responselivedata_3)。

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/fragment/SenderFragment.kt){ .md-button }
