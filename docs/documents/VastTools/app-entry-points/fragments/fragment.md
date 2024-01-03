# Fragment

`VastFragment` 是基于 [Fragment](https://developer.android.com/reference/androidx/fragment/app/Fragment.html) 进行封装的。

## 快速使用

我们以 `VastVbVmFragment` 为例，向你展示了如何将其添加到你的项目当中：

```kotlin
class VideosFragment : VastVbVmFragment<FragmentVideosBinding, SharedVM>() {

}
```

当然，如果你的项目中没有采用 [ViewBinding](https://developer.android.com/topic/libraries/view-binding?hl=zh-cn) ，你可以继承 `VastVmFragment` ，在此情况下你需要将 `layoutId` 设定为对应的布局id，例如：

```kotlin
class SenderFragment(override val layoutId: Int = R.layout.fragment_sender) :
    VastVmFragment<SharedVM>() {
    
}
```

## 含参数 ViewModel 的创建

如果 `ViewModel` 含有参数，你应该重写 `createViewModel` 方法。

```kotlin
class ParamVM(val param: String) : ViewModel()
```

```kotlin
class SampleVbVmFragment : VastVbVmFragment<FragmentSampleVbVmBinding, ParamVM>() {

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        ...
    }

    override fun createViewModel(modelClass: Class<out ViewModel>): ViewModel {
        return ParamVM(defaultTag)
    }

}
```

## ViewModel Owner

当 `setVmBySelf` 为 true 时，表示 Fragment 的 ViewModel 会自行保留。当你希望 ViewModel 被其关联的 Activity 保留时，请将 `setVmBySelf` 设置为 false 。

你可以通过修改 [SenderFragment](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/fragment/SenderFragment.kt) 的 `setVmBySelf` 返回值来查看 [ReceiverFragment](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/fragment/ReceiverFragment.kt) 是否会接收到数据更新。

```kotlin
override fun setVmBySelf(): Boolean = false
```

## 默认日志标志

你可以通过 `getDefaultTag` 返回值作为日志的默认 TAG，是 `Fragment` 的类名。

```kotlin
Log.i(getDefaultTag(), "这是一个日志。")
```

## 进行网络请求

在 [ImagesFragment](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/fragment/ImagesFragment.kt) 为你演示了如何通过 `getResponseBuilder` 进行网络请求。

```kotlin
getBinding().refresh.setOnRefreshListener {
    getResponseBuilder().suspendWithListener({
        OpenApi().create(OpenApiService::class.java).getImages(0, 10)
    }) {
        ... // 进行数据处理
    }
}
```

!!! warning "过时说明"

    `getResponseBuilder` 方法在 [0.5.3](https://ave.entropy2020.cn/version/VastTools/#053) 版本已被废弃。

## 获取视图绑定对象

通过 `getBinding()` 你可以获取对应的视图绑定对象。

```kotlin
getBinding().view
```

!!! danger "关于生命周期的说明"

    你不应该在 `onDestroyView` 之后再调用 `getBinding()` 方法，因为这会导致空异常。

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/fragment){ .md-button }
