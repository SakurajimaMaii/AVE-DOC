# Resources

## findByContext

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

`findByContext` provides you with [Context](https://developer.android.com/reference/android/content/Context) so that you can find the resources.

=== "kotlin"

    ```kotlin
    val drawable = findByContext {
        AppCompatResources.getDrawable(this, R.drawable.android_logo)
    }
    ```

=== "java"

    ```java
    try {
        drawable = ResUtilsKt.findByContext(context ->
            AppCompatResources.getDrawable(context, R.drawable.android_logo)
        );
    } catch (Exception e) {
        throw new RuntimeException(e);
    }
    ```

## findByResources

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

`findByResources` provides you with [Resources](https://developer.android.com/reference/android/content/res/Resources) so that you can find the resources.

=== "kotlin"

    ```kotlin
    val drawable = findByResources { res, theme ->
        ResourcesCompat.getDrawable(res, R.drawable.android_logo, theme)
    }
    ```

=== "java"

    ```java
    try {
        drawable = ResUtilsKt.findByResources((resources, theme) ->
            ResourcesCompat.getDrawable(resources, R.drawable.android_logo, theme)
        );
    } catch (Exception e) {
        throw new RuntimeException(e);
    }
    ```
