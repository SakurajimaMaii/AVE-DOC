# 非空变量

## NotNUllVar

[:octicons-tag-24: Version 0.0.1](https://ave.entropy2020.cn/version/core/#001)

有的时候需要创建可变非空变量，这就需要使用 `NotNUllVar` 来实现。

```kotlin
private var age by NotNUllVar<Int>()
```

`NotNUllVar` 同时提供一个属性 `once` ，如果你希望该变量只能被初始化一次，可以指定 `once` 为 `true`

```kotlin
private var age by NotNUllVar<Int>(once = true)
```

## NotNullOrDefault

[:octicons-tag-24: Version 0.0.6](https://ave.entropy2020.cn/version/core/#006)

获取非空变量。如果没有设置其他值，则 **defaultValue** 将用作变量的值，并且不允许更改。

```kotlin
private var fileMaxSize by NotNullOrDefault(1024L)
```
