# Not-null variables

## NotNUllVar

[:octicons-tag-24: Version 0.0.1](https://ave.entropy2020.cn/version/VastCore/#001)

NotNUllVar allows you to create non-null variables.

```kotlin
private var age by NotNUllVar<Int>()
```

### Once set

if true, the variable will only set by once, false otherwise.

## NotNullOrDefault

[:octicons-tag-24: Version 0.0.6](https://ave.entropy2020.cn/version/VastCore/#006)

Getting a non-null variable. If no other value is set, the **defaultValue**
will be used as the value of the variable and no changes are allowed.

```kotlin
private var fileMaxSize by NotNullOrDefault(1024L)
```
