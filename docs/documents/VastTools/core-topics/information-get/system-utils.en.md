# System information

![SystemUtils](../img/system_utils.png){ align=right width="300" }

- System language

    ```kotlin
    SystemUtils.systemLanguage
    ```

- System language list

    ```kotlin
    for(locale in systemLanguageList){
        // to do something
    }
    ```

- Android version

    ```kotlin
    SystemUtils.systemAndroidVersion
    ```

- End-user-visible name

    ```kotlin
    SystemUtils.systemModel
    ```

- Consumer-visible brand

    ```kotlin
    SystemUtils.deviceBrand
    ```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/informationget/SystemInfo.kt){ .md-button }
