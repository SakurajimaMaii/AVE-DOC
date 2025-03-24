# 资源获取

## findByContext

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

`findByContext` 为你提供了 [Context](https://developer.android.com/reference/android/content/Context) 以便你查找对应的资源。

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

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

`findByResources` 为你提供了 [Resources](https://developer.android.com/reference/android/content/res/Resources) 以便你查找对应的资源。

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
