# 版本信息

## 版本适配拓展

[:octicons-tag-24: Version 1.2.1](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#121)

通常在版本适配中需要编写以下代码：

```kotlin
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.UPSIDE_DOWN_CAKE) {

}
```

此时可以使用 [`fromApi34()`](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.os.extension/from-api34.html) 进行替代：

=== "kotlin"

    ```kotlin
    fromApi34 {
        // 其他代码
    }
    ```

=== "java"

    ```java
    BuildExt.fromApi34(() -> {
        // 其他代码
        return null;
    });
    ```
