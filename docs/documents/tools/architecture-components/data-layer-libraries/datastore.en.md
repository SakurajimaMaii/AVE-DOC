# Extension for DataStore

In order to make you use `DataStore` more convenient, `VastTools` provides extension functions. 

## Store key-value pairs with Preferences DataStore by extension functions

### Create a Preferences DataStore

Use the property delegate created by `preferencesDataStore` to create an instance of `Datastore<Preferences>`. Call it once at the top level of your kotlin file, and access it through this property throughout the rest of your application. This makes it easier to keep your `DataStore` as a singleton. 

```kotlin
val Context.dataStore: DataStore<Preferences> by 
    preferencesDataStore(name = "settings")
```

### Implement IDataStoreOwner

[:octicons-tag-24: Version 0.5.6](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#056)

```kotlin
object ThemeDs : IDataStoreOwner {
    override val dataStore: DataStore<Preferences> =
        ContextHelper.getAppContext().dataStore

    val isDark by boolean(false)
}
```

### Read from a Preferences DataStore

[:octicons-tag-24: Version 0.5.6](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#056)

The following example shows you that `Boolean` type data can be read from `Preferences DataStore` by calling `asNotNullFlow` in Compose .

```kotlin
val darkTheme by ThemeDs.isDark.asNotNullFlow().collectAsState(false)
```

### Write to a Preferences DataStore

[:octicons-beaker-24: Version 0.5.1](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#051)

The following example shows you that `Boolean` type data can be written to `Preferences DataStore` in Compose .

```kotlin
val coroutineScope = rememberCoroutineScope()

Switch(checked = darkTheme, onCheckedChange = { value ->
    coroutineScope.launch {
        ThemeDs.isDark.set(value)
    }
})
```
