# 系统信息

`SystemUtils` 为你提供了获取系统信息的一些方法。

![SystemUtils](../img/system_utils.png){ align=right width="300" }

- 获取系统语言

    ```kotlin
    SystemUtils.systemLanguage
    ```

- 返回所有已安装语言环境的数组

    ```kotlin
    for(locale in systemLanguageList){
        // to do something
    }
    ```

- 返回系统的安卓版本

    ```kotlin
    SystemUtils.systemAndroidVersion
    ```

- 返回最终产品的最终用户可见名称

    ```kotlin
    SystemUtils.systemModel
    ```

- 返回与产品/硬件相关联的消费者可见品牌（如果有）

    ```kotlin
    SystemUtils.deviceBrand
    ```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/informationget/SystemInfo.kt){ .md-button }
