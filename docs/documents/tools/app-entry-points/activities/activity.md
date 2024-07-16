# Activity

`VastActivity` 组件为你提供了开发所必须的 `Activity` 组件。

## 快速使用

我们以 `VastVbVmActivity` 为例，你无需去手动初始化 `ViewBinding` 和 `ViewModel` 。

```kotlin
class ExampleActivity : VastVbVmActivity<ActivityExampleBinding, SampleSharedVM>() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        getBinding().addOne.setOnClickListener {
            getViewModel().addOne()
        }

        getViewModel().count.observe(this){
            getBinding().count.text = it.toString()
        }
    }
}
```

!!! danger "setContentView说明"

    请不要在子类中调用 `setContentView` 方法，不然会导致视图绑定失效。

<figure markdown>
  ![快速使用](../img/activity_example.gif){ width="200" }
  <figcaption>快速使用</figcaption>
</figure>

## 隐藏 ActionBar

`enableActionBar` 必须在 `super.onCreate` 之后调用。

```kotlin
class ExampleActivity : VastVbVmActivity<ActivityExampleBinding, SampleSharedVM>() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableActionBar(false) // 不显示ActionBar
        ... // 其他设置
    }

}
```

<figure markdown>
  ![隐藏ActionBar](../img/hide_action_bar.jpg){ width="200" }
  <figcaption>隐藏ActionBar</figcaption>
</figure>

## 启动全面屏模式

`enableFullScreen` 必须在 `super.onCreate` 之后调用。

```kotlin
class ExampleActivity : VastVbVmActivity<ActivityExampleBinding, SampleSharedVM>() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableFullScreen(false) // 启用全面屏
        ... // 其他设置
    }

}
```

<figure markdown>
  ![使用全面屏](../img/enable_full_screen.jpg){ width="200" }
  <figcaption>使用全面屏</figcaption>
</figure>

## 含参数 ViewModel 的创建

如果 `ViewModel` 含有参数，你应该重写 `createViewModel` 方法。

```kotlin
class ParamVM(val param: String) : ViewModel()
```

```kotlin
class ThemeActivity : VastVbVmActivity<ActivityThemeBinding, ParamVM>() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        ... // 其他设置
    }

    override fun createViewModel(modelClass: Class<out ViewModel>): ViewModel {
        return ParamVM("This is a param")
    }

}
```

## 设置启动页面

下面展示了如何设置启动页面，必须在 `super.onCreate` 前面调用。

```kotlin
class MainActivity : VastVbActivity<ActivityMainBinding>() {

    private lateinit var mSplashScreen: SplashScreen

    override fun onCreate(savedInstanceState: Bundle?) {
        mSplashScreen = installSplashScreen()
        super.onCreate(savedInstanceState)
        ... // 其他设置
    }

}    
```

## 默认日志标志

你可以通过 `getDefaultTag` 作为日志的默认TAG，是 `Activity` 的类名。

```kotlin
Log.i(getDefaultTag(), "这是一个日志。")
```

## Snackbar

`VastVbActivity` `VastVbVmActivity` `VastVmActivity` 提供了默认的 `Snacker` 对象 `mSnackbar` 。

```kotlin
getSnackbar().setText(ResUtils.getString(R.string.loading_page)).show()
```

<figure markdown>
  ![Snackbar](../img/snackbar.jpg){ width="200" }
  <figcaption>Snackbar</figcaption>
</figure>


## Context

你可以通过 `getContext()` 对象获取 `Activity` 上下文。

## 获取视图绑定对象

通过 `getBinding()` 你可以获取对应的视图绑定对象。

```kotlin
getBinding().view
```
