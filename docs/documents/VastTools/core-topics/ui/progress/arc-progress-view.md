# ArcProgressView

`ArcProgressView` 是圆形进度条。

<figure markdown>
  ![圆形进度条](../img/arc_progress_view.gif){ width="250" }
  <figcaption>圆形进度条。</figcaption>
</figure>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

```xml
<com.ave.vastgui.tools.view.progress.ArcProgressView
    android:id="@+id/arcProgressView"
    android:layout_width="200dp"
    android:layout_height="200dp"
    android:layout_gravity="center_horizontal"
    android:layout_margin="10dp"
    app:arc_progress_background_width="20dp"
    app:progress_text_size="12sp" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 属性设置

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

`ArcProgressView` 目前支持你自定义以下内容：

- 进度条起始点颜色
- 进度条结束点颜色
- 进度条背景色
- 进度条颜色（支持渐变色）
- 进度条文字颜色
- 进度条文字大小
- 进度条是否显示起始点和结束点
- 进度条样式

```kotlin
// Here is an example
val colors = intArrayOf(
    ColorUtils.colorHex2Int("#F60C0C"),
    ColorUtils.colorHex2Int("#F3B913"),
    ColorUtils.colorHex2Int("#E7F716"),
    ColorUtils.colorHex2Int("#3DF30B"),
    ColorUtils.colorHex2Int("#0DF6EF"),
    ColorUtils.colorHex2Int("#0829FB"),
    ColorUtils.colorHex2Int("#B709F4")
)
val pos = floatArrayOf(
    1f / 7, 2f / 7, 3f / 7, 4f / 7, 5f / 7, 6f / 7, 1f
)

getBinding().downloadCv.apply {
    setProgressShader(
        LinearGradient(-700f, 0f, 700f, 0f, colors, pos, Shader.TileMode.CLAMP)
    )
}
```

### 半径设置

!!! notes "半径参数数值设置"

    进度条的半径参数仅允许在 xml 内进行定义，无法进行动态修改，这是合理的。

使用 `arc_progress_radius` 属性来指定半径。

```xml
<com.ave.vastgui.tools.view.progress.ArcProgressView
    android:id="@+id/downloadCv"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:arc_progress_radius="200dp"
    ... />
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/view/ArcProgressViewActivity.kt){ .md-button }
