# 字符串匹配

## 检查字符串是否为邮箱

=== "Kotlin"

    ```kotlin
    "12345678@qq.com".isEmail()
    ```

=== "Java"

    ```java
    StrRegexKt.isEmail("12345678@qq.com");
    ```

## 检查字符串是否是QQ号

=== "Kotlin"

    ```kotlin
    "123456710".isQQ()
    ```

=== "Java"

    ```java
    StrRegexKt.isQQ("123456710");
    ```

## 检查字符串是否是电话号码

目前仅支持中国地区的号码验证，参考自 [2021 手机号正则表达式](https://www.jianshu.com/p/1e8eab706a63)

=== "Kotlin"

    ```kotlin
    "16612341213".isPhoneNumber()
    ```

=== "Java"

    ```java
    StrRegexKt.isPhoneNumber("16612341213");
    ```

## 检查字符串是否是数字

=== "Kotlin"

    ```kotlin
    "123456789".isNumeric()
    ```

=== "Java"

    ```java
    StrRegexKt.isNumeric("123456789");
    ```
