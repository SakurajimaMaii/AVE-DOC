# StrRegex

## Check if string is Email address

=== "Kotlin"

    ```kotlin
    "12345678@qq.com".isEmail()
    ```

=== "Java"

    ```java
    StrRegexKt.isEmail("12345678@qq.com");
    ```

## Check if string is QQ number

=== "Kotlin"

    ```kotlin
    "123456710".isQQ()
    ```

=== "Java"

    ```java
    StrRegexKt.isQQ("123456710");
    ```

## String verified according to the Chinese phone number

Currently only mobile phone number verification in China is supported, refer to [2021 手机号正则表达式](https://www.jianshu.com/p/1e8eab706a63)

=== "Kotlin"

    ```kotlin
    "16612341213".isPhoneNumber()
    ```

=== "Java"

    ```java
    StrRegexKt.isPhoneNumber("16612341213");
    ```

## Check if string is a number

=== "Kotlin"

    ```kotlin
    "123456789".isNumeric()
    ```

=== "Java"

    ```java
    StrRegexKt.isNumeric("123456789");
    ```
