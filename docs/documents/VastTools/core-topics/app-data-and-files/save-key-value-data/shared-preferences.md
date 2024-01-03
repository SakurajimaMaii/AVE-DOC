# 适用于 SharedPreferences 的拓展

目前支持的数据类型：

- String
- Set< String>
- Int
- Long
- Float
- Boolean
- Double

## 快速开始

[:octicons-tag-24: Version 0.5.6](https://ave.entropy2020.cn/version/VastTools/#056)

- 实现 `ISharedPreferencesOwner`

    ```kotlin
    object SpExample : ISharedPreferencesOwner {
        override val name: String = "Sp的名称"
        override val kv: SharedPreferences = ... // SharedPreferences 对象

        // 声明存储的字段
        var isDark by boolean(false)
    }
    ```

- 向共享偏好中写入数据

    ```kotlin
    SpExample.isDark = !SpExample.isDark
    ```

- 从共享偏好中读出数据

    ```kotlin
    val isDark = SpExample.isDark
    ```

- 从共享偏好中清除数据

    调用 `clearAll()` 从 `SpExample` 中删除所有值。

    ```kotlin
    SpExample.clearAll()
    ```
