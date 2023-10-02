# ViewModel reflection

## Create viewModel

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

`reflectViewModel` can create `ViewModel` by reflection.

Define the `ReflectBaseActivity1`

```kotlin
abstract class ReflectBaseActivity1<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewModel
    protected val mViewModel: VM by lazy {
        reflectViewModel(this.javaClass, this)
    }

}
```

Extend `ReflectBaseActivity1`

```kotlin
class ReflectViewModel1() : ViewModel(){
    ... // Content
}

class ReflectActivity1 : ReflectBaseActivity1<ActivityMyBinding, ReflectViewModel1>() {
    ... // Content
}
```

## Create viewModel(have constructor parameter)

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Define `ReflectBaseActivity2` and `createViewModel` .

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
 
Extend `ReflectBaseActivity2` and override `createViewModel` .

```kotlin
class ReflectViewModel2(val parameter: String) : ViewModel(){
    ... // Content
}

class ReflectActivity2 : ReflectBaseActivity2<ActivityMyBinding, ReflectViewModel2>() {

    override fun createViewModel(modelClass: Class<out ViewModel>): MyViewModel2 {
        return MyViewModel2("parameter")
    }

}
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/java/com/ave/vastgui/app/activity/reflectexample){ .md-button }
