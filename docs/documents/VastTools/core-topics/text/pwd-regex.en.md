# PwdRegex

By using `PwdRegex` , you can check if the password strength meets the requirements.

## Quick start

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

```kotlin
"852Vast.".isPwd(RwdStrength3)
```

## Password strength

### Default value

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

Four password strength are provided by default:

- PwdStrength1：Password contains at least one letter and one number.
- PwdStrength2：Password contains at least one uppercase letter, one lowercase letter and one number.
- PwdStrength3：Password contains at least one letter, one number and one special character.
- RwdStrength4：Password contains at least one uppercase letter, one lowercase letter, one number and one special character.

!!! note "Special character"

    Special character include !@#$%^&*.

### Customize password strength

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

By implementing `PwdStrength` , you can customize the expression corresponding to the password strength, for example:

```kotlin
object YourRwdStrength : PwdStrength {
    override val regex: String
        get() = "(?=.*[A-Z])(?=.*[a-z])(?=.*\\d)(?=.*[!@#\\\$%\\^&\\*\\.])."
}
```

## Common combination shielding

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

`isPwd` provides the parameter `shouldNotAppear`, through which you can specify combinations that should not appear in the password, for example:

```kotlin
"852admin".isPwd(RwdStrength3, shouldNotAppear = arrayOf("123","admin"))
```

## Sample code

[Sample Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/text/PwdRegex.kt){ .md-button }
