# ArcProgressView

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/arc_progress_view.mp4" type="video/mp4">
    </video>
</center>

## Quick start

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

```xml
<com.ave.vastgui.tools.view.progress.ArcProgressView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## Progress width

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Width of pogress can be set by `arc_progress_width` or calling `mProgressWidth` .

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

|                         20dp                         |                       10dp                        |
| :--------------------------------------------------: | :-----------------------------------------------: |
| ![Width 20dp](../img/progress_55.jpg){ width="150" } | ![Width 10dp](../img/width_10.jpg){ width="150" } |

## Color of startpoint and endpoint circle

[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

Color of startpoint circle can be set by `arc_progress_startpoint_circle_color` or calling `mStartpointCircleColor` .

Color of endpoint circle can be set by `arc_progress_endpoint_circle_color` or calling `mEndpointCircleColor` .

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

|              Progress 0              |              Progress 55               |                 Startpoint circle                  |                Endpoint circle                 |
| :----------------------------------: | :------------------------------------: | :------------------------------------------------: | :--------------------------------------------: |
| ![Progress 0](../img/progress_0.jpg) | ![Progress 55](../img/progress_55.jpg) | ![Startpoint circle](../img/startpoint_circle.jpg) | ![Endpoint circle](../img/endpoint_circle.jpg) |

## Radius of endpoint circle

[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055)

Radius of endpoint circle can be set by `arc_progress_endpoint_circle_radius` or calling `mEndpointCircleRadius` .

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

## Shader

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Shader of progress can be set by calling `mProgressShader` .

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

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/ArcProgressViewActivity.kt){ .md-button }
