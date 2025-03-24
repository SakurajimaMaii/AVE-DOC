# 指示器

指示器默认会以 **圆点** 形式显示你当前所在的页面。

<figure markdown>
  ![Vp2IndicatorView](../img/vp2_indicator_view.gif){ width="250" }
</figure>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

=== "xml"

    ```xml
    <com.ave.vastgui.tools.view.vp2indicator.Vp2IndicatorView
        android:id="@+id/vp2indicator"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        app:indicator_item_count="3" />
    ```

=== "compose"

    ```kotlin
    AndroidView(factory = { ctx ->
        Vp2IndicatorView(ctx).apply {
            setIndicatorItemCount(5)
            setIndicatorCircleRadius(20f)
        }
    })
    ```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 附加到 ViewPager2

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

调用 `attachToViewPager2` ，你可以将指示器附加到 `ViewPager2` 上。

!!! warning "attachToViewPager2"

    该方法被调用后将不再允许手动设置指示器数量和当前被选中的指示器。

```kotlin
mBinding.vp2indicator.attachToViewPager2(mBinding.vp2)
```

## 设置圆点指示器半径

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

调用 `setIndicatorCircleRadius` 设置圆形指示器半径。

```kotlin
mBinding.vp2indicator.setIndicatorCircleRadius(8F.DP)
```

<figure markdown>
  ![默认指示器大小](../img/default_size.jpg){ width="250" }
</figure>

<figure markdown>
  ![修改指示器大小](../img/change_size.jpg){ width="250" }
</figure>

## 设置圆点指示器颜色

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

调用 `setSelectedColor` 和 `setUnSelectedColor` 来修改指示器选中和未选中状态颜色。

```kotlin
mBinding.vp2indicator.apply {
    setSelectedColor(R.color.tomato)
    setUnSelectedColor(R.color.limegreen)
    ... // 其他设置
}
```

<figure markdown>
  ![修改指示器颜色](../img/change_color.jpg){ width="250" }
</figure>

## 设置指示器间距

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

调用 `setIndicatorItemDistance` 来修改指示器间距。

```kotlin
mBinding.vp2indicator.setIndicatorItemDistance(10F.DP)
```

## 设置指示器类型

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

调用 `setIndicatorStyle` 来设置指示器类型，目前支持两种

- CIRCLE：默认的圆形指示器
- BITMAP：指定对应的Bitmap为指示器形状

## 设置 Bitmap 作为指示器

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

下面的示例为你展示了如何设置三角形 bitmap 为指示器。

```kotlin
mBinding.vp2indicator.apply {
    setIndicatorStyle(Vp2IndicatorType.BITMAP)
    setBitmapSize(20f.DP.toInt(),20f.DP.toInt())
    setSelectedBitmap(R.drawable.ic_indicator_select)
    setUnSelectedBitmap(R.drawable.ic_indicator_unselect)
    ... // 其他设置
}
```

<figure markdown>
  ![修改指示器为bitmap](../img/bitmap.jpg){ width="250" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/Vp2IndicatorActivity.kt){ .md-button }
