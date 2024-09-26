# 通过反射获取 ViewModel

## 创建 ViewModel 

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

`reflectViewModel` 通过反射来获取 `ViewModel` 对象。

定义 `ReflectBaseActivity1`

```kotlin
abstract class ReflectBaseActivity1<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewModel
    protected val mViewModel: VM by lazy {
        reflectViewModel(this.javaClass, this)
    }

}
```

继承 `ReflectBaseActivity1`

```kotlin
// 声明 ViewModel
// 注意这里是无参数
class ReflectViewModel1() : ViewModel(){
    ... // Content
}

class ReflectActivity1 : ReflectBaseActivity1<ActivityMyBinding, ReflectViewModel1>() {
    ... // Content
}
```

## 创建有含参构造函数的 ViewModel 

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

`reflectViewModel` 默认情况下提供了无参数 ViewModel 构造方法给 ViewModelProvider.Factory ，如果你想传入带参数的 ViewModel ，可以参考下面的示例：

定义 `ReflectBaseActivity2` ，并添加一个 `createViewModel` 方法给 `reflectViewModel` 。

```kotlin
abstract class ReflectBaseActivity2<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewModel
    protected val mViewModel: VM by lazy {
        reflectViewModel(this.javaClass, this) {
            return@reflectViewModel createViewModel(it)
        }
    }

    protected open fun createViewModel(modelClass: Class<out ViewModel>): ViewModel {
        return modelClass.newInstance()
    }

}
```
 
继承 `ReflectBaseActivity2` ，并重写 `createViewModel` 方法。

```kotlin
// 声明 ViewModel
// 注意这里有参数
class ReflectViewModel2(val parameter: String) : ViewModel(){
    ... // Content
}

class ReflectActivity2 : ReflectBaseActivity2<ActivityMyBinding, ReflectViewModel2>() {

    override fun createViewModel(modelClass: Class<out ViewModel>): MyViewModel2 {
        return MyViewModel2("这是一个参数")
    }

}
```

## 示例代码

[示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/reflection/ReflectBaseActivity.kt){ .md-button }
