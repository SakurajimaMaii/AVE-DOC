# 密码验证

`PwdRegex` 提供了可拓展的密码验证方法。

## 快速使用

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

=== "kotlin"

    ```kotlin
    // 判断密码是否至少包含一个字母，一个数字还有一个特殊字符
    "852Vast.".isPwd(RwdStrength3)
    ```

=== "java"

    ```java
    PwdRegexKt.isPwd("852Vast.", PwdStrength1.INSTANCE);
    ```

## 密码强度

### 默认强度

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

`PwdRegex` 默认提供了四种密码强度：

- PwdStrength1：要求密码至少包含一个字母和一个数字。
- PwdStrength2：要求密码至少包含一个大写字母、一个小写字母和一个数字。
- PwdStrength3：要求密码至少包含一个字母和一个数字，以及一个特殊字符。
- RwdStrength4：要求密码至少包含一个大写字母、一个小写字母和一个数字，以及一个特殊字符。

!!! note "特殊字符说明"

    特殊字符包括 !@#$%^&*.

### 自定义密码强度

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

通过实现 `PwdStrength` 接口，你可以自定义密码强度对应的正则表达式，例如：

=== "kotlin"

    ```kotlin
    object YourRwdStrength : PwdStrength {
        override val regex: String
            get() = "(?=.*[A-Z])(?=.*[a-z])(?=.*\\d)(?=.*[!@#\\\$%\\^&\\*\\.])."
    }
    ```

=== "java"

    ```java
    class YourRwdStrength implements PwdStrength{
        @NonNull
        @Override
        public String getRegex() {
            return "(?=.*[A-Z])(?=.*[a-z])(?=.*\\d)(?=.*[!@#\\\$%\\^&\\*\\.]).";
        }
    }
    ```

## 常见组合屏蔽

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

`isPwd` 提供了参数 `shouldNotAppear` ，通过该参数你可以指定密码中不应该出现的组合，例如：

=== "kotlin"

    ```kotlin
    "852admin".isPwd(RwdStrength3, shouldNotAppear = arrayOf("123","admin"))
    ```

=== "java"

    ```java
    PwdRegexKt.isPwd("852admin", RwdStrength3.INSTANCE, 6, 20, new String[]{"123", "admin"});
    ```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/text/PwdRegex.kt){ .md-button }
