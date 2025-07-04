# 裁剪控件

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

`CropViewLayout` 是一个裁剪控件，目的是帮助你快速构建自己的裁剪页面。

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/crop_view_layout.mp4" type="video/mp4">
    </video>
</center>


## 快速使用

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```xml
<com.ave.vastgui.tools.view.cropview.CropViewLayout
    android:id="@+id/cropview_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## 调用裁剪

### 调用系统裁剪

你可以使用 [CropIntent](https://sakurajimamaii.github.io/AVE-DOC/documents/tools/core-topics/intent/crop-intent/) 来调用系统裁剪。

### 调用 VastCropActivity

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

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

!!! info "VastCropActivity"

    更多使用还请参考 [VastCropActivity.kt](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/kotlin/com/ave/vastgui/tools/activity/app/VastCropActivity.kt) 的定义。

## 设置预览框的类型

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `crop_frame_type` 或者调用 `cropFrameType` 来设置预览框的形状，目前支持四种：

|  类型  |                          示例                           |   类型    |                             示例                              |
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

## 设置预览框的大小

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

预览框的大小和预览框的形状有关，如果预览框的形状是 `RECTANGLE` ，则可以通过 `crop_frame_width` 和 `crop_frame_height` 或者调用 `setCropFrameSize(Float, Float)` 来设置预览框的大小。

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

如果形状是 `CIRCLE` ， `SQUARE` 或 `GRID9` ，则可以通过 `crop_frame_size` 或者调用 `setCropFrameSize(Float)` 来设置预览框的大小。

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

## 设置预览框的蒙版颜色

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; 更新：[:octicons-clock-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

可以通过 `crop_mask_layer_color` 或者调用 `setCropMaskColor` 来设置蒙版颜色。

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

!!! note "蒙版颜色说明"

    建议采用带透明度的颜色效果会更好。

<figure markdown>
  ![CropViewLayout with mask color](../img/mask_color.jpg){ width="250" }
</figure>

## 设置设置预览框的边框颜色

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

可以通过 `crop_frame_stroke_color` 或者调用 `setCropFrameStrokeColor` 来设置边框颜色。

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

## 获取裁剪照片

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

!!! note "过时说明" 

    因为 `setDrawingCacheEnabled` ， `buildDrawingCache` 相关 API 在 API 28 过时，因而提供了两种方式获取裁剪照片。

### 对 Android 9 的适配(API 28开始)

```kotlin
val bitmap: Bitmap? = 
    binding.cropViewLayout.getCroppedImageApi28(outputX, outputY)
```

### 对 Android 8 及以下的适配

```kotlin
val bitmap: Bitmap? = 
    binding.cropViewLayout.getCroppedImage(outputX, outputY)
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/CropActivity.kt){ .md-button }
