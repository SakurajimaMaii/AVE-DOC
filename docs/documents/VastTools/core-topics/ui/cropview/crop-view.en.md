# CropViewLayout

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/crop_view_layout.mp4" type="video/mp4">
    </video>
</center>


## Quick start

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

```xml
  <com.ave.vastgui.tools.view.cropview.CropViewLayout
      android:id="@+id/cropViewLayout"
      android:layout_width="match_parent"
      android:layout_height="match_parent" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Call crop

### Call system cropping application

Using [CropIntent](https://ave.entropy2020.cn/documents/VastTools/core-topics/intent/CropIntent/) to call the system cropping application.

### VastCropActivity

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

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

Click [VastCropActivity](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/activity/app/VastCropActivity.kt) to get more information.

## Frame type

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

The frame type can be set by `setCropFrameType` .

|Type|Example|Type|Example|
|:-:|:-:|:-:|:-:|
|CIRCLE|![Frame circle](../img/frame_cricle.jpg){ width="250" }|SQUARE|![Frame square](../img/frame_square.jpg){ width="250" }|
|GRID9|![Frame grid9](../img/frame_grid9.jpg){ width="250" }|RECTANGLE|![Frame rectangle](../img/frame_rectangle.jpg){ width="250" }|

```kotlin
getBinding().cropViewLayout.setCropFrameType(CropFrameType.CIRCLE)
```

## Frame size

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

Calling `setCropFrameSize` to set the frame size.

```kotlin
getBinding().cropViewLayout.setCropFrameSize(previewWidth, previewHeight)
```

!!! warning "Size of rectangle frame type"

    The different length and width settings will only take effect when the preview frame type is **RECTANGLE**. Otherwise, the smaller value of the set length and width will be used as the actual preview frame size.

## Mask color

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

Calling `setCropMaskColor` to set the mask color.

```kotlin
getBinding().cropViewLayout.setCropMaskColor(color)
```

!!! note "Alpha of mask color"

    It is recommended to use a color with transparency for better effect.

<figure markdown>
  ![CropViewLayout with mask color](../img/mask_color.jpg){ width="250" }
</figure>

## Stroke color

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

Calling `setCropFrameStrokeColor` to set the stroke color of the frame.

```kotlin
val color = ColorUtils.colorHex2Int("#e74c3c")

getBinding().cropViewLayout.setCropFrameStrokeColor(color)
```

<figure markdown>
  ![CropViewLayout with stroke color](../img/stroke_color.jpg){ width="250" }
</figure>

## Output image

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

### Compatibility with Android 9(API 28)

```kotlin
val bitmap:Bitmap? = 
    getBinding().cropViewLayout.getCroppedImageAboveApi28(outputX,outputY)
```

### Compatibility under Android 9

```kotlin
val bitmap:Bitmap? =
    getBinding().cropViewLayout.getCroppedImageUnderApi28(outputX,outputY)
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/CropImageActivity.kt){ .md-button }
