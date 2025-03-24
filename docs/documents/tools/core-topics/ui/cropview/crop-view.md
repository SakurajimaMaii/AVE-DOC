# 裁剪控件

`CropViewLayout` 是一个裁剪控件，目的是帮助你快速构建自己的裁剪页面。

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/crop_view_layout.mp4" type="video/mp4">
    </video>
</center>


## 快速使用

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```xml
  <com.ave.vastgui.tools.view.cropview.CropViewLayout
      android:id="@+id/cropViewLayout"
      android:layout_width="match_parent"
      android:layout_height="match_parent" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 调用裁剪

### 调用系统裁剪

你可以使用 [CropIntent](https://sakurajimamaii.github.io/AVE-DOC/documents/VastTools/core-topics/intent/CropIntent/) 来调用系统裁剪。

### 调用 VastCropActivity

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

`VastCropActivity` 是默认提供的裁剪应用，你可以通过下面的方式来轻松的使用它。

```xml
// 在 AndroidManifest.xml 中声明
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
// 使用 intent 来启动
val intent = Intent(this, VastCropActivity::class.java).apply {
    data = originalImageUri
    putExtra(VastCropActivity.FRAME_TYPE, VastCropActivity.FRAME_TYPE_GRID9)
    putExtra(VastCropActivity.OUTPUT_X, 300f)
    putExtra(VastCropActivity.OUTPUT_Y, 300f)
}
```

更多使用还请参考 [VastCropActivity.kt](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/activity/app/VastCropActivity.kt) 的定义。

## 设置预览框的类型

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

调用 `setCropFrameType` 来设置预览框的形状，目前支持四种：

|类型|示例|类型|示例|
|:-:|:-:|:-:|:-:|
|CIRCLE|![Frame circle](../img/frame_cricle.jpg){ width="250" }|SQUARE|![Frame square](../img/frame_square.jpg){ width="250" }|
|GRID9|![Frame grid9](../img/frame_grid9.jpg){ width="250" }|RECTANGLE|![Frame rectangle](../img/frame_rectangle.jpg){ width="250" }|

```kotlin
getBinding().cropViewLayout.setCropFrameType(CropFrameType.CIRCLE)
```

## 设置预览框的大小

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

调用 `setCropFrameSize` 来设置预览框的大小。

```kotlin
getBinding().cropViewLayout.setCropFrameSize(previewWidth, previewHeight)
```

!!! warning "关于预览框的大小设置说明"

    只有当预览框的类型是 **RECTANGLE** 时设置的不相同的长和宽才会生效，否则会取设置的长和宽中的较小值作为实际的预览框尺寸。

## 设置预览框的蒙版颜色

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

调用 `setCropMaskColor` 来设置蒙版颜色。

```kotlin
// 设置颜色
getBinding().cropViewLayout.setCropMaskColor(color)
```

!!! note "蒙版颜色说明"

    建议采用带透明度的颜色效果会更好。

<figure markdown>
  ![CropViewLayout with mask color](../img/mask_color.jpg){ width="250" }
</figure>

## 设置设置预览框的边框颜色

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

调用 `setCropFrameStrokeColor` 来设置蒙版颜色

```kotlin
// 获取颜色
val color = ColorUtils.colorHex2Int("#e74c3c")

// 设置颜色
getBinding().cropViewLayout.setCropFrameStrokeColor(color)
```

<figure markdown>
  ![CropViewLayout with stroke color](../img/stroke_color.jpg){ width="250" }
</figure>

## 获取裁剪照片

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

!!! note "过时说明" 

    因为 `setDrawingCacheEnabled` ， `buildDrawingCache` 相关 API 在 API 28 过时，因而提供了两种方式获取裁剪照片。

### 对 Android 9 的适配(API 28开始)

```kotlin
val bitmap:Bitmap? = 
    getBinding().cropViewLayout.getCroppedImageAboveApi28(outputX,outputY)
```

### 对 Android 8 及以下的适配

```kotlin
val bitmap:Bitmap? =
    getBinding().cropViewLayout.getCroppedImageUnderApi28(outputX,outputY)
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/CropImageActivity.kt){ .md-button }
