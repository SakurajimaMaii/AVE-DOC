# RequestBuilder

`RequestBuilder` 主要用来构建请求示例。

## 快速开始

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

创建由 Service 接口定义的 API 端点的实现。

```kotlin
val baseUrl = ....
RequestBuilder(baseUrl).create(QRService::class.java)
```

配合 [Request2](https://ave.entropy2020.cn/documents/VastTools/core-topics/connectivity/performing-network-operations/Request2/) 使用

```kotlin
val baseUrl = ....
RequestBuilder(baseUrl)
    .getApi(QRService::class.java) {
        generateQRCode(DateUtils.getCurrentTime())
    }.collect {

    }
```

## RequestBuilder 配置

`RequestBuilder` 提供了默认实现，但是如果你想要自定义可以通过继承 `RequestBuilder` 来重写对应的方法。

```kotlin
class MyRequestBuilder: RequestBuilder(Constant.ROOT_URL) {

    override fun setTimeOut(): Long {
        return 10L
    }
    
}
```

### 设置超时时间

通过重载 `setTimeOut` 方法，你可以设置 `call` ， `read` ， `connect` ， `write` 的超时时间。

```kotlin
override fun setTimeOut(): Long {
    return 10L
}
```

### 配置 okhttp 客户端

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

```kotlin
override fun okHttpConfiguration(builder: OkHttpClient.Builder) {
    builder.apply { 
        ... // 自定义OKHttpClient的配置
    }
}
```

### 配置 retrofit 客户端

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

```kotlin
override fun retrofitConfiguration(builder: Retrofit.Builder) {
    
}
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/net/NetRequestBuilder.kt){ .md-button }
