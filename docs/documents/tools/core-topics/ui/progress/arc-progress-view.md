# ArcProgressView

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/arc_progress_view.mp4" type="video/mp4">
    </video>
</center>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

```xml
<com.ave.vastgui.tools.view.progress.ArcProgressView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## 进度条宽度

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

通过 `arc_progress_width` 或者调用 `mProgressWidth` 可以设置进度条的宽度。

=== "Kotlin"

    ```kotlin
    mBinding.arcProgressView.mProgressWidth = 10f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.ArcProgressView
        ... 
        app:arc_progress_width="10dp" />
    ```

|                     宽度20dp                     |                     宽度10dp                      |
| :----------------------------------------------: | :-----------------------------------------------: |
| ![Width 20dp](../img/progress_55.jpg){ width="150" } | ![Width 10dp](../img/width_10.jpg){ width="150" } |

## 端点颜色

[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

通过 `arc_progress_startpoint_circle_color` 或者调用 `mStartpointCircleColor` 可以设置进度条起点圆的颜色。

通过 `arc_progress_endpoint_circle_color` 或者调用 `mEndpointCircleColor` 可以设置进度条终点圆的颜色。

=== "Kotlin"

    ```kotlin
    mBinding.arcProgressView.mStartpointCircleColor =
        ColorUtils.colorHex2Int("#e84118")

    mBinding.arcProgressView.mEndpointCircleColor = 
        ColorUtils.colorHex2Int("#e84118")
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.ArcProgressView
        ... 
        app:arc_progress_startpoint_circle_color="#e84118"
        app:arc_progress_endpoint_circle_color="#e84118" />
    ```

|              默认进度0               |                 进度55                 |                       起点圆                       |                     终点圆                     |
| :----------------------------------: | :------------------------------------: | :------------------------------------------------: | :--------------------------------------------: |
| ![Progress 0](../img/progress_0.jpg) | ![Progress 55](../img/progress_55.jpg) | ![Startpoint circle](../img/startpoint_circle.jpg) | ![Endpoint circle](../img/endpoint_circle.jpg) |

## 终点端点半径

[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055)

通过 `arc_progress_endpoint_circle_radius` 或者调用 `mEndpointCircleRadius` 可以设置终点端点半径。

=== "Kotlin"

    ```kotlin
    mBinding.arcProgressView.mEndpointCircleRadius = 
        15f.DP.coerceAtLeast(recommendedRadius())
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.ArcProgressView
        ... 
        app:arc_progress_endpoint_circle_radius="20dp" />
    ```

<figure markdown>
  ![Progress endpoint radius](../img/arc_progress_endpoint_radius.jpg){ width="200" }
</figure>

## 着色器

[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055)

通过调用 `mProgressShader` 可以设置渐变进度条。

```kotlin
val colors = intArrayOf(
    ... // Color-int
)
val pos = floatArrayOf(
    ... // The relative positions [0..1] of each corresponding color in the colors array.
)
getBinding().arcProgressView.mProgressShader = LinearGradient(
    -700f, 0f, 700f, 0f,
    colors, pos,
    Shader.TileMode.CLAMP
)
```

<figure markdown>
  ![Progress shader](../img/shader.jpg){ width="200" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/ArcProgressViewActivity.kt){ .md-button }
