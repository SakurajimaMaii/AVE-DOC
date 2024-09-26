# ResponseLiveData

## ResponseLiveData 的数据状态

`StateLiveData` 目前支持五种状态：

- Success 可以表示数据获取成功
- Failed 可以表示数据获取失败
- Error 可以表示数据获取错误
- Empty 可以表示获取的是空数据
- Clear 可以表示清除状态

## 快速开始

### 创建 ResponseLiveData

```kotlin
private val _sentence = ResponseMutableLiveData<Sentences>()
val sentence: ResponseLiveData<Sentences>
    get() = _sentence
```

### 观察 ResponseLiveData

#### 观察对象值发生变化

对于 `requestResponse` ，你可以使用 `observe` 将其添加到观察者列表中。

```kotlin
mViewModel.sentence.observe(requireActivity()) {
    mBinding.sentence.text = it.toString()
}
```


#### 观察状态发生变化

[:octicons-tag-24: Version 0.3.0](https://ave.entropy2020.cn/version/tools/#030)

对于 `requestResponse` ，调用 `observeState` 方法将状态添加到观察者列表中。

!!! note "关于 onSuccess 方法的说明"

    对于 `onSuccess` 来说，你只能观察到值对应的状态而并非数据值。

```kotlin
mViewModel.sentence.observeState(requireActivity()) {
    onSuccess = {
        mLogger.d("请求成功")
    }
    onError = {
        mLogger.d("遇到异常${it?.message}")
    }
    onFailed = { code, message ->
        mLogger.d("请求失败，错误代码${code}，错误信息${message}")
    }
}
```

### 更新 ResponseLiveData

`ResponseLiveData` 只提供了 `postValueAndSuccess` 方法来更新对象值，其它情况下你只能更新 `ResponseLiveData` 对象的状态。

- `onFailed` 提供了两个参数允许你传递**错误代码**和**错误信息**两个内容。
- `postError` 提供了一个参数允许你传递**异常信息**。

```kotlin
OpenApi().create(OpenApiService::class.java)
    .sentences()
    .request {
        onSuccess = { _sentence.postValueAndSuccess(it) }
        onError = { _sentence.postError(it) }
        onFailed = { code, message -> _sentence.postFailed(code, message) }
    }
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/fragment/ReceiverFragment.kt){ .md-button }
