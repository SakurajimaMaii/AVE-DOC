# Fragment

`VastFragment` 是基于 [Fragment](https://developer.android.com/reference/androidx/fragment/app/Fragment.html) 进行封装的。

## 快速使用

我们以 `VastVbVmFragment` 为例，向你展示了如何将其添加到你的项目当中：

```kotlin
class SampleVbVmFragment : VastVbVmFragment<FragmentSampleVbVmBinding, SampleSharedVM>() {

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)

        getBinding().addOne.setOnClickListener {
            ... //click event
        }
    }

}
```

当然，如果你的项目中没有采用 [ViewBinding](https://developer.android.com/topic/libraries/view-binding?hl=zh-cn) ，你可以继承 `VastVmFragment` ，在此情况下你需要将 `layoutId` 设定为对应的布局id，例如：

```kotlin
class SampleVmFragment(override val layoutId: Int = R.layout.fragment_sample_vm) : 
    VastVmFragment<SampleSharedVM>() {

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        ... //Something to do
    }

}
```

## 含参数ViewModel的创建

如果 `ViewModel` 含有参数，你应该重写 `createViewModel` 方法。

```kotlin
class SampleVbVmFragment : VastVbVmFragment<FragmentSampleVbVmBinding, SampleSharedVM>() {

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        ...
    }

    override fun createViewModel(modelClass: Class<out ViewModel>): ViewModel {
        return SampleSharedVM(defaultTag)
    }

}
```

## ViewModel Owner

当 `setVmBySelf` 为 true 时，表示 Fragment 的 ViewModel 会自行保留。当您希望 ViewModel 被其关联的 Activity 保留时，请将 `setVmBySelf` 设置为 false。

```kotlin
override fun setVmBySelf(): Boolean = false
```

## 默认日志标志

你可以通过 `defaultTag` 作为日志的默认TAG，是 `Activity` 的名字。

```kotlin
LogUtils.i(getDefaultTag(), this@SampleVbVmFragment::class.java.simpleName)
```

## 进行网络请求

```kotlin
getResponseBuilder().suspendWithListener({
    NetworkRetrofitBuilder().create(UserService::class.java).generateQRCode(DateUtils.currentTime)
}){
    onSuccess = {

    }
    onFailed = {

    }
}
```

## 获取视图绑定对象

通过 `getBinding()` 你可以获取对应的视图绑定对象。

```kotlin
getBinding().view
```

!!! danger "关于生命周期的说明"

    你不应该在 `onDestroyView` 之后再调用 `getBinding()` 方法，因为这会导致空异常。

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/java/com/ave/vastgui/app/fragment){ .md-button }
