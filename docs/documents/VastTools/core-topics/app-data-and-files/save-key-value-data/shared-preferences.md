# 适用于 SharedPreferences 的拓展

为了方便用户对 `SharedPreferences` 进行操作，提供了如下的拓展方法：

`fun SharedPreferences.string(defaultValue: String? = null): ReadWriteProperty<Any, String>`

目前支持的数据类型：

- String
- Set< String>
- Int
- Long
- Float
- Boolean
- Double

## 向共享偏好中写入数据

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

```kotlin
// sp 是一个 SharedPreferences 对象
var count by sp.float()
count = 1f
```

## 从共享偏好中读出数据

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

```kotlin
// sp 是一个 SharedPreferences 对象
var count by sp.float()
val value = count
```

## 从共享偏好中清除数据

[:octicons-beaker-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

调用 `clearAll()` 从 `SharedPreferences` 中删除所有值。

```kotlin
sp.clearAll()
```
