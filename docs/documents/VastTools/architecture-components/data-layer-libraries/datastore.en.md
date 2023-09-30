# Extension for DataStore

In order to make you use `DataStore` more convenient, `VastTools` provides extension functions. 

## Store key-value pairs with Preferences DataStore by extension functions

### Create a Preferences DataStore

Use the property delegate created by `preferencesDataStore` to create an instance of `Datastore<Preferences>`. Call it once at the top level of your kotlin file, and access it through this property throughout the rest of your application. This makes it easier to keep your `DataStore` as a singleton. 

```kotlin
val Context.dataStore: DataStore<Preferences> by 
    preferencesDataStore(name = "settings")
```

### Write to a Preferences DataStore

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

The following example shows you that `Boolean` type data can be written to `Preferences DataStore` by calling **`saveBoolean`** in `Compose` .

```kotlin
val checkState = remember { mutableStateOf(false) }
val coroutineScope = rememberCoroutineScope()

Switch(checked = checkState.value, onCheckedChange = {
    checkState.value = it
    coroutineScope.launch {
        dataStore.saveBoolean("isdark", it)
    }
})
```

### Read from a Preferences DataStore

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

The following example shows you that `Boolean` type data can be read from `Preferences DataStore` by calling **`readBooleanFlow`** in `Compose` .

```kotlin
val context = LocalContext.current
val darkFlow = remember {
    context.dataStore.readBooleanFlow("isdark",false)
}

val isThemeInDarkState = darkFlow.collectAsState(initial = false)
```
