# Resources

## findByContext

> Add:[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

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

> Add:[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

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

Extension functions

> Add:[:octicons-tag-24: Version 1.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

| Method Name                         | Description                                           |
| ----------------------------------- | ----------------------------------------------------- |
| `Context.drawable(int)`             | Retrieves drawable resource                           |
| `Context.vectorDrawable(int)`       | Retrieves VectorDrawable resource                     |
| `Context.color(int)`                | Retrieves color resource                              |
| `Context.colorStateList(int)`       | Retrieves ColorStateList resource                     |
| `Context.string(int)`               | Retrieves string resource                             |
| `Context.stringArray(int)`          | Retrieves string array resource                       |
| `Context.dimension(int)`            | Retrieves dimension resource (in pixels)              |
| `Context.dimensionPixelSize(int)`   | Retrieves dimension resource (in pixel size)          |
| `Context.dimensionPixelOffset(int)` | Retrieves dimension resource (in offset)              |
| `Context.integer(int)`              | Retrieves integer resource                            |
| `View.drawable(int)`                | Retrieves drawable resource for View                  |
| `View.vectorDrawable(int)`          | Retrieves VectorDrawable resource for View            |
| `View.color(int)`                   | Retrieves color resource for View                     |
| `View.colorStateList(int)`          | Retrieves ColorStateList resource for View            |
| `View.string(int)`                  | Retrieves string resource for View                    |
| `View.stringArray(int)`             | Retrieves string array resource for View              |
| `View.dimension(int)`               | Retrieves dimension resource for View (in pixels)     |
| `View.dimensionPixelSize(int)`      | Retrieves dimension resource for View (in pixel size) |
| `View.dimensionPixelOffset(int)`    | Retrieves dimension resource for View (in offset)     |
| `View.integer(int)`                 | Retrieves integer resource for View                   |
