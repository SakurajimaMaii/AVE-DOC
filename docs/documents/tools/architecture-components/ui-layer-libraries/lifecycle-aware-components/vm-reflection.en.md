# ViewModel reflection

## Create viewModel

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

`reflectViewModel` can create `ViewModel` by reflection.

Defining the base class, taking `ReflectBaseActivity1` as an example.

```kotlin
abstract class ReflectBaseActivity1<VB : ViewBinding, VM : ViewModel> : AppCompatActivity() {

    // ViewModel
    protected val mViewModel: VM by lazy {
        reflectViewModel(this.javaClass, this)
    }

}
```

Making your `Activity` extends the `ReflectBaseActivity1` , for example:

```kotlin
class ReflectViewModel1() : ViewModel(){
    ... // Content
}

class ReflectActivity1 : ReflectBaseActivity1<ActivityMyBinding, ReflectViewModel1>() {
    ... // Content
}
```

## Create viewModel(Constructor with parameters)

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

In order to create a ViewModel**(Constructor with parameters)** , you can take the following code as an example:

Defining the base class, taking `ReflectBaseActivity2` as an example. And providing a function like `createViewModel` so that the subclass can override it to return the ViewModel instance which have parameters in constructor.

Defining the `ReflectBaseActivity2`:

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

Making your `Activity` extends the `ReflectActivity2` and override the `createViewModel` , for example:

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

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/reflection/ReflectBaseActivity.kt){ .md-button }
