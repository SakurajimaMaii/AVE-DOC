# 适用于 DataStore 的拓展

为了方便用户对 `DataStore` 进行操作，提供了对应的的拓展方法：

## 使用拓展方法在 Preferences DataStore 中进行存储

### 创建 Preferences DataStore

使用由 `preferencesDataStore` 创建的属性委托来创建 `Datastore<Preferences>` 实例。在您的 Kotlin 文件顶层调用该实例一次，便可在应用的所有其余部分通过此属性访问该实例。这样可以更轻松地将 `DataStore` 保留为单例。

```kotlin
val Context.dataStore: DataStore<Preferences> by 
    preferencesDataStore(name = "settings")
```

### 将内容写入 Preferences DataStore

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

下面的示例为你展示了在 `Compose` 中通过调用 **`saveBoolean`** 可以将 `Boolean` 类型数据写入 `Preferences DataStore` 中。

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

### 从 Preferences DataStore 读取内容

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

下面的示例为你展示了在 `Compose` 中通过调用 **`readBooleanFlow`** 可以将 `Boolean` 类型数据从`Preferences DataStore` 中读出。

```kotlin
val context = LocalContext.current
val darkFlow = remember {
    context.dataStore.readBooleanFlow("isdark",false)
}

val isThemeInDarkState = darkFlow.collectAsState(initial = false)
```
