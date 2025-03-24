# Extension for SharedPreferences

In order to make you use `SharedPreferences` more convenient, `VastTools` provides following extension functions. 

`fun SharedPreferences.string(defaultValue: String? = null): ReadWriteProperty<Any, String>`

Currently support data type:

- String
- Set< String>
- Int
- Long
- Float
- Boolean
- Double

## Get started 

[:octicons-tag-24: Version 0.5.6](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#056)

- Implement `ISharedPreferencesOwner`

    ```kotlin
    object SpExample : ISharedPreferencesOwner {
        override val name: String = "Sp name"
        override val kv: SharedPreferences = ... // SharedPreferences instance

        // Declare stored fields
        var isDark by boolean(false)
    }
    ```

- Write to shared preferences

    ```kotlin
    SpExample.isDark = !SpExample.isDark
    ```

- Read from shared preferences

    ```kotlin
    val isDark = SpExample.isDark
    ```

- Clear shared preferences

    Calling `clearAll()` to remove all values ​​from `SharedPreferences`.

    ```kotlin
    sp.clearAll()
    ```
