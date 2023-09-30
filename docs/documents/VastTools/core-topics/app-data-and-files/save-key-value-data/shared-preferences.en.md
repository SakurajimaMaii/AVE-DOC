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

## Write to shared preferences

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

```kotlin
// sp is SharedPreferences
var count by sp.float()
count = 1f
```

## Read from shared preferences

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

```kotlin
// sp is SharedPreferences
var count by sp.float()
val value = count
```

## Clear shared preferences

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

Use `clearAll()` to remove all values ​​from `SharedPreferences`.

```kotlin
sp.clearAll()
```
