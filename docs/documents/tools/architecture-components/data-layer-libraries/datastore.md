# 适用于 DataStore 的拓展

为了方便用户对 `DataStore` 进行操作，提供了对应的的拓展方法：

## 使用拓展方法在 Preferences DataStore 中进行存储

### 创建 Preferences DataStore

使用由 `preferencesDataStore` 创建的属性委托来创建 `Datastore<Preferences>` 实例。在您的 Kotlin 文件顶层调用该实例一次，便可在应用的所有其余部分通过此属性访问该实例。这样可以更轻松地将 `DataStore` 保留为单例。

```kotlin
val Context.dataStore: DataStore<Preferences> by 
    preferencesDataStore(name = "settings")
```

### 实现 IDataStoreOwner

[:octicons-tag-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

```kotlin
object ThemeDs : IDataStoreOwner {
    override val dataStore: DataStore<Preferences> =
        ContextHelper.getAppContext().dataStore

    val isDark by boolean(false)
}
```

### 从 Preferences DataStore 读取内容

[:octicons-tag-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

下面的示例为你展示了在 `Compose` 中通过调用 `asNotNullFlow` 可以将 `Boolean` 类型数据从 `Preferences DataStore` 中读出。

```kotlin
val darkTheme by ThemeDs.isDark.asNotNullFlow().collectAsState(false)
```

### 将内容写入 Preferences DataStore

[:octicons-tag-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

下面的示例为你展示了在 `Compose` 中将 `Boolean` 类型数据写入 `Preferences DataStore` 中。

```kotlin
val coroutineScope = rememberCoroutineScope()

Switch(checked = darkTheme, onCheckedChange = { value ->
    coroutineScope.launch {
        ThemeDs.isDark.set(value)
    }
})
```
