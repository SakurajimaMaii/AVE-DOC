# 位图

`BmpUtils` 主要为你提供了关于 [Bitmap](https://developer.android.com/reference/kotlin/android/graphics/Bitmap?hl=en) 的一些方法

## 位图合并

下面的示例使用纯色 `Bitmap` 作为演示。

```kotlin
internal fun getColorBitmap(@ColorInt colorInt: Int, width: Int, height: Int) =
    Bitmap.createBitmap(width, height, Bitmap.Config.ARGB_8888).also {
        it.eraseColor(colorInt)
    }
```

### 上下重叠

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

调用 `mergeBitmap` 可以将两个位图上下重叠合并在一起，合并后的大小由底部位图决定。

```kotlin
val mergeBitmap = BmpUtils.mergeBitmap(
    getColorBitmap(Color(0xFF6ab04c).toArgb(),200,200),
    getColorBitmap(Color(0xFFeb4d4b).toArgb(),300,300)
)
```

目前 `mergeBitmap` 提供五种位置可供选择。

=== "MergePosition.LT"

    <figure markdown>
      ![MergePosition.LT](../img/merge_position_lt.png){ width="150" }
    </figure>


=== "MergePosition.LB"

    <figure markdown>
      ![MergePosition.LB](../img/merge_position_lb.png){ width="150" }
    </figure>

=== "MergePosition.RT"

    <figure markdown>
      ![MergePosition.RT](../img/merge_position_rt.png){ width="150" }
    </figure>

=== "MergePosition.RB"

    <figure markdown>
      ![MergePosition.RB](../img/merge_position_rb.png){ width="150" }
    </figure>

=== "MergePosition.CENTER"

    <figure markdown>
      ![MergePosition.CENTER](../img/merge_position_center.png){ width="150" }
    </figure>

### 左右拼接

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

调用 `mergeBitmapLR` 可以将两个位图左右拼接合并在一起，你可以决定是小图放大还是大图缩小。

```kotlin
val mergeBitmap = BmpUtils.mergeBitmapLR(
    getColorBitmap(Color(0xFF6ab04c).toArgb(), 200, 200),
    getColorBitmap(Color(0xFFeb4d4b).toArgb(), 300, 300),
    MergeScale.BIG_REDUCE
)
```

|           参数           |                                       示例图                                        |
| :----------------------: | :---------------------------------------------------------------------------------: |
| MergeScale.SMALL_ENLARGE | ![MergePosition.SMALL_ENLARGE](../img/merge_scale_small_enlarge.png){ width="292" } |
|  MergeScale.BIG_REDUCE   |    ![MergePosition.BIG_REDUCE](../img/merge_scale_big_reduce.png){ width="195" }    |

### 上下拼接

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

调用 `mergeBitmapTB` 可以将两个位图上下拼接合并在一起，你可以决定是小图放大还是大图缩小。

```kotlin
val mergeBitmap = BmpUtils.mergeBitmapTB(
    getColorBitmap(Color(0xFF6ab04c).toArgb(), 200, 200),
    getColorBitmap(Color(0xFFeb4d4b).toArgb(), 300, 300),
    MergeScale.SMALL_ENLARGE
)
```

|           参数           |                                         示例图                                         |         参数          |                                      示例                                       |
| :----------------------: | :------------------------------------------------------------------------------------: | :-------------------: | :-----------------------------------------------------------------------------: |
| MergeScale.SMALL_ENLARGE | ![MergePosition.SMALL_ENLARGE](../img/merge_scale_small_enlarge_tb.png){ width="146" } | MergeScale.BIG_REDUCE | ![MergePosition.BIG_REDUCE](../img/merge_scale_big_reduce_tb.png){ width="97" } |

## 通过 Base64 获取位图

通过 `getBitmapFromBase64` 方法将 **base64**字符串转换成 `Bitmap` 对象。

```kotlin
val base64 =  .....
val base64Bitmap = BmpUtils.getBitmapFromBase64(base64)
```

[查看示例Base64](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/graphics/bitmap/Base64.txt){ .md-button }

## 通过 Drawable 获取位图

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

`getBitmapFromDrawable` 可以将 `Drawable` 转换成 `Bitmap` 对象。

```kotlin
val context = LocalContext.current
val bitmap = BmpUtils.getBitmapFromDrawable(R.drawable.ic_github, context)
Image(bitmap = bitmap.asImageBitmap(), contentDescription = "测试图片")
```

## 位图缩放

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

如下图所示，使用 `scaleBitmap` 可以将位图放大到你需要的尺寸。

```kotlin
val size = 50F.DP.toInt()
val requiredSize = 100F.DP.toInt()
val bitmap = BmpUtils.scaleBitmap(
    getColorBitmap(Color(0xFF6ab04c).toArgb(), size, size),
    requiredSize, requiredSize
)
```

<figure markdown>
  ![ScaleBitmap](../img/scale_bitmap.png){ width="200" }
  <figcaption>左图为原图，右图为缩放后的图片</figcaption>
</figure>

## 获取尺寸

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

`getBitmapWidthHeight` 允许你传入对应的解码方式并返回解码后的位图尺寸。

```kotlin
val context = LocalContext.current
val (width, height) = BmpUtils.getBitmapWidthHeight { options ->
    BitmapFactory.decodeResource(context.resources, R.drawable.github, options)
}
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/graphics/bitmap/Bitmap.kt){ .md-button }
