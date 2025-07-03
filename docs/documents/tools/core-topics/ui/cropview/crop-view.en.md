# CropViewLayout

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/crop_view_layout.mp4" type="video/mp4">
    </video>
</center>


## Quick start

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```xml
<com.ave.vastgui.tools.view.cropview.CropViewLayout
    android:id="@+id/cropview_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## Use of Cropping

### Calling the system cropping application

Using [CropIntent](https://sakurajimamaii.github.io/AVE-DOC/documents/tools/core-topics/intent/crop-intent/) to call the system cropping application.

### VastCropActivity

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

`VastCropActivity` is the default cropping application. You can easily use it in the following ways.

```xml
<activity
    android:name="com.ave.vastgui.tools.activity.app.VastCropActivity"
    android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
</activity>
```

```kotlin
val intent = Intent(this, VastCropActivity::class.java).apply {
    data = originalImageUri
    putExtra(VastCropActivity.FRAME_TYPE, VastCropActivity.FRAME_TYPE_GRID9)
    putExtra(VastCropActivity.OUTPUT_X, 300f)
    putExtra(VastCropActivity.OUTPUT_Y, 300f)
}
```

!!! info "VastCropActivity"

    Click [VastCropActivity](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/kotlin/com/ave/vastgui/tools/activity/app/VastCropActivity.kt) to get more information.

## Frame type

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

The frame type can be set by  `crop_frame_type` or calling `cropFrameType` .

|  Type  |                         Example                         |   Type    |                            Example                            |
| :----: | :-----------------------------------------------------: | :-------: | :-----------------------------------------------------------: |
| CIRCLE | ![Frame circle](../img/frame_cricle.jpg){ width="250" } |  SQUARE   |    ![Frame square](../img/frame_square.jpg){ width="250" }    |
| GRID9  |  ![Frame grid9](../img/frame_grid9.jpg){ width="250" }  | RECTANGLE | ![Frame rectangle](../img/frame_rectangle.jpg){ width="250" } |

=== "Kotlin"

    ```kotlin
    binding.cropViewLayout.cropFrameType = CropFrameType.CIRCLE
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.cropview.CropViewLayout
        ...
        app:crop_frame_type="circle" />
    ```

## Frame size

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

The size of the preview frame is related to the shape of the preview frame, if the shape of the preview frame is `RECTANGLE`, the size of the preview frame can be set by `crop_frame_width` and `crop_frame_height` or call `setCropFrameSize(Float, Float)`.

=== "Kotlin"

    ```kotlin
    binding.cropViewLayout.setCropFrameSize(50f.DP, 50f.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.cropview.CropViewLayout
        ...
        app:crop_frame_width="50dp"
        app:crop_frame_height="50dp" />
    ```

If the shape is `CIRCLE`, `SQUARE` or `GRID9`, the size of the preview frame can be set by `crop_frame_size` or call `setCropFrameSize(Float)`.

=== "Kotlin"

    ```kotlin
    binding.cropViewLayout.setCropFrameSize(50f.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.cropview.CropViewLayout
        ...
        app:crop_frame_size="50dp" />
    ```

## Mask color

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; Update:[:octicons-clock-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

The mask color can be set by  `crop_mask_layer_color` or calling `setCropMaskColor` .

=== "Kotlin"

    ```kotlin
    binding.cropViewLayout.setCropMaskColor(Color.RED)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.cropview.CropViewLayout
        ...
        app:crop_mask_layer_color="@color/red" />
    ```

!!! note "Alpha of mask color"

    It is recommended to use a color with transparency for better effect.

<figure markdown>
  ![CropViewLayout with mask color](../img/mask_color.jpg){ width="250" }
</figure>

## Stroke color

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

The stroke color of the frame can be set by  `crop_frame_stroke_color` or calling `setCropFrameStrokeColor` .

=== "Kotlin"

    ```kotlin
    binding.cropViewLayout.setCropFrameStrokeColor(Color.RED)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.cropview.CropViewLayout
        ...
        app:crop_frame_stroke_color="@color/red" />
    ```

<figure markdown>
  ![CropViewLayout with stroke color](../img/stroke_color.jpg){ width="250" }
</figure>

## Output image

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

### Compatibility with Android 9(API 28)

```kotlin
val bitmap:Bitmap? = binding.cropViewLayout.getCroppedImageApi28(outputX,outputY)
```

### Compatibility under Android 9

```kotlin
val bitmap:Bitmap? = binding.cropViewLayout.getCroppedImage(outputX,outputY)
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/CropActivity.kt){ .md-button }
