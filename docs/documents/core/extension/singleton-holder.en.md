# SingletonHolder

Use SingletonHolder to build a singleton with parameters.

## Get started

```kotlin
class Singleton private constructor(name: String) {

    ... // do other things.

    companion object:SingletonHolder<Singleton,String>(::Singleton)

}

// Get the singleton.
private val singleton by lazy {
    Singleton.getInstance(defaultLogTag())
}
```

## Example code

[Example code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/model/Singleton.kt){ .md-button }
