# 常见问题

- **在 Android SDK 24 以下调用 `void log(Supplier<String> messageSupplier);` 遭遇异常。**

    这是因为 [Supplier](https://developer.android.com/reference/java/util/function/Supplier) 是在 Android SDK 24 才加入的，因此可以使用以下方式来解决：

    ```kotlin title="app/build.gradle.kts"
    android {
        compileOptions {
            // ...
            isCoreLibraryDesugaringEnabled = true
        }
    }

    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.1.2")
    ```

    > 完整内容参考 [Java 8 及更高版本 API 脱糖支持（Android Gradle 插件 4.0.0 及更高版本）](https://developer.android.com/studio/write/java8-support?hl=zh-cn#library-desugaring)