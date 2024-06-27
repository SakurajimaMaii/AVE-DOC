# ViewBinding reflection

## Quick start

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Define `reflectViewBinding` .

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

Extend `ReflectBaseActivity1` .

```kotlin
class ReflectActivity1 : ReflectBaseActivity1<ActivityMyBinding, ReflectViewModel1>() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        mBinding.personRv.adapter = VbAdapter2(persons)
        mBinding.personRv.layoutManager = LinearLayoutManager(this)
    }

}
```

## Reduce recursion

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

`reflectViewBinding` provides a `base` parameter that allows you to reduce the number of recursive searches.

```kotlin
abstract class ReflectBaseActivity1<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewBinding
    protected val mBinding: VB by lazy {
        reflectViewBinding(ReflectBaseActivity1::class.java)
    }

}
```

## Proguard rules

```xml
-keep public interface androidx.viewbinding.ViewBinding
-keep class * implements androidx.viewbinding.ViewBinding{
    *;
}

-keep class * extends com.ave.vastgui.tools.activity.VastActivity { *;}
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/reflection/ReflectActivity.kt){ .md-button }
