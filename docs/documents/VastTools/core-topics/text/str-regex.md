# 字符串匹配

`RegexUtils` 提供了一些字符串的正则检查

## 检查字符串是否为邮箱

=== "kotlin"

    ```kotlin
    "12345678@qq.com".isEmail()
    ```

=== "java"

    ```java
    StrRegexKt.isEmail("12345678@qq.com");
    ```

## 检查字符串是否是QQ号

=== "kotlin"

    ```kotlin
    "123456710".isQQ()
    ```

=== "java"

    ```java
    StrRegexKt.isQQ("123456710");
    ```

## 检查字符串是否是电话号码

目前仅支持中国地区的号码验证，参考自 [2021 手机号正则表达式](https://www.jianshu.com/p/1e8eab706a63)

=== "kotlin"

    ```kotlin
    "16612341213".isPhoneNumber()
    ```

=== "java"

    ```java
    StrRegexKt.isPhoneNumber("16612341213");
    ```

## 检查字符串是否是数字

=== "kotlin"

    ```kotlin
    "123456789".isNumeric()
    ```

=== "java"

    ```java
    StrRegexKt.isNumeric("123456789");
    ```
