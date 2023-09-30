# SpEncrypted

`SpEncrypted` is used to open an instance of encrypted SharedPreferences. 

## Get started

```kotlin
// Declare your own SharedPreferences.
class EncryptedSp(name: String) {

    // Get the SharedPreferences instance by SpEncrypted.getInstance()
    private val sp by lazy{
        SpEncrypted.getInstance(name).getSharedPreferences()
    }

    // Declare variables.
    var count by sp.float()
    
}

// Use it.
private val mSp by lazy { EncryptedSp(defaultLogTag()) }

// Set values.
mSp.count = 1f
// Get values.
val count = mSp.count
```

## Example Code

[Example Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/sharedpreferences/SpEncryptedExample.kt){ .md-button }
