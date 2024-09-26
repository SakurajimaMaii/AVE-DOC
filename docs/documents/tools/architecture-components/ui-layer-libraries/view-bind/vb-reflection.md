# 使用反射获取视图拓展

## 快速开始

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

通过在基类内调用 `reflectViewBinding` 方法来通过反射获取 `ViewBinding` 对象。

```kotlin
abstract class ReflectBaseActivity1<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewBinding
    protected val mBinding: VB by lazy {
        reflectViewBinding()
    }

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(mBinding.root)
    }

}
```

继承 `ReflectBaseActivity1`

```kotlin
class ReflectActivity1 : ReflectBaseActivity1<ActivityMyBinding, ReflectViewModel1>() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        mBinding.personRv.adapter = VbAdapter2(persons)
        mBinding.personRv.layoutManager = LinearLayoutManager(this)
    }

}
```

## 减少递归

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

`reflectViewBinding` 提供了 `base` 参数允许你减少递归检索的次数。

```kotlin
abstract class ReflectBaseActivity1<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewBinding
    protected val mBinding: VB by lazy {
        reflectViewBinding(ReflectBaseActivity1::class.java)
    }

}
```

## 混淆配置

如果你开启了混淆需要进行以下配置

```xml
# 对于 ViewBinding 的处理
-keep public interface androidx.viewbinding.ViewBinding
-keep class * implements androidx.viewbinding.ViewBinding{
    *;
}

# 排除 VastActivity 的子类
-keep class * extends com.ave.vastgui.tools.activity.VastActivity { *;}
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/reflection/ReflectActivity.kt){ .md-button }
