# 资源获取

## findByContext

> 添加：[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

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

> 添加：[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

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

## 拓展函数

> 添加：[:octicons-tag-24: Version 1.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

| 方法名                              | 说明                                   |
| ----------------------------------- | -------------------------------------- |
| `Context.drawable(int)`             | 获取 drawable 资源                     |
| `Context.vectorDrawable(int)`       | 获取 VectorDrawable 资源               |
| `Context.color(int)`                | 获取颜色资源                           |
| `Context.colorStateList(int)`       | 获取 ColorStateList 资源               |
| `Context.string(int)`               | 获取字符串资源                         |
| `Context.stringArray(int)`          | 获取字符串数组资源                     |
| `Context.dimension(int)`            | 获取维度资源（以像素值返回）           |
| `Context.dimensionPixelSize(int)`   | 获取维度资源（以像素大小返回）         |
| `Context.dimensionPixelOffset(int)` | 获取维度资源（以偏移量返回）           |
| `Context.integer(int)`              | 获取整数资源                           |
| `View.drawable(int)`                | 获取 View 的 drawable 资源             |
| `View.vectorDrawable(int)`          | 获取 View 的 VectorDrawable 资源       |
| `View.color(int)`                   | 获取 View 的颜色资源                   |
| `View.colorStateList(int)`          | 获取 View 的 ColorStateList 资源       |
| `View.string(int)`                  | 获取 View 的字符串资源                 |
| `View.stringArray(int)`             | 获取 View 的字符串数组资源             |
| `View.dimension(int)`               | 获取 View 的维度资源（以像素值返回）   |
| `View.dimensionPixelSize(int)`      | 获取 View 的维度资源（以像素大小返回） |
| `View.dimensionPixelOffset(int)`    | 获取 View 的维度资源（以偏移量返回）   |
| `View.integer(int)`                 | 获取 View 的整数资源                   |
