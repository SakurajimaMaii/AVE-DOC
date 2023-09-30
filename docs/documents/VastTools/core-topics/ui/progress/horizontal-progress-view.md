# HorizontalProgressView

横向进度条共有下列三种形式

<figure markdown>
  ![横向进度条](../img/horizontal_progress_view.gif){ width="250" }
  <figcaption>横向进度条</figcaption>
</figure>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

在示例图中，从上到下依次是 `HorizontalProgressView` ， `HorizontalTextProgressView` 和 `LineTextProgressView` 。

=== "HorizontalProgressView"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalProgressView
        android:id="@+id/horizontalProgressView"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_margin="10dp" />
    ```

=== "HorizontalTextProgressView"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalTextProgressView
        android:id="@+id/horizontalTextProgressView"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_margin="10dp" />
    ```

=== "LineTextProgressView"

    ```xml
    <com.ave.vastgui.tools.view.progress.LineTextProgressView
        android:id="@+id/lineTextProgressView"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_margin="10dp" />
    ```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 更新进度

调用 `setCurrentProgress` 来设置当前进度条的进度。

```kotlin
mBindings.horizontalProgressView.refreshWithInvalidate {
    setCurrentProgress(progress.toFloat())
}
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/view/HorizontalProgressViewActivity.kt){ .md-button }
