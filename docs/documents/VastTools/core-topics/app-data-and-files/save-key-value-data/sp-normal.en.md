# SpNormal

!!! tip

    For security reasons, I prefer to use `SpEncrypted`.

`SpNormal` is used to open an instance of encrypted SharedPreferences. 

## Get started

```kotlin
// Declare your own SharedPreferences.
class NormalSp(name: String) {

    // Get the SharedPreferences instance by SpNormal.getInstance()
    private val sp by lazy{
        SpNormal.getInstance(name).getSharedPreferences()
    }

    // Declare variables.
    var count by sp.float()
}

// Use it.
private val mSp by lazy { NormalSp(defaultLogTag()) }

// Set values.
mSp.count = 1f
// Get values.
val count = mSp.count
```

## Example Code

[Example Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/sharedpreferences/SpNormalExample.kt){ .md-button }
