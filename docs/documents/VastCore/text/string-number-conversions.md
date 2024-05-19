# 文本转换

[:octicons-tag-24: Version 0.1.0](https://ave.entropy2020.cn/version/VastCore/#010)

能够确保更加安全将字符串转换成数字。

=== "kotlin"

    ```kotlin
    val value = "123".safeToInt(1)
    ```

=== "java"

    ```java
    int value = StringsKt.safeToInt("123", 1);
    ```

| 方法               | 描述                            |
| :----------------- | :------------------------------ |
| `safeToInt`        | 将 `String` 转换成 `Int`        |
| `safeToLong`       | 将 `String` 转换成 `Long`       |
| `safeToFloat`      | 将 `String` 转换成 `Float`      |
| `safeToDouble`     | 将 `String` 转换成 `Double`     |
| `safeToBigInteger` | 将 `String` 转换成 `BigInteger` |
| `safeToBigDecimal` | 将 `String` 转换成 `BigDecimal` |
