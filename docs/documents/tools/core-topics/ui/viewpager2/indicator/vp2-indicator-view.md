# 指示器

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

指示器默认会以 **圆点** 形式显示你当前所在的页面。

<figure markdown>
  ![Vp2IndicatorView](../img/vp2_indicator_view.gif){ width="250" }
</figure>

## 快速使用

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

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

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

调用 `attachToViewPager2` ，你可以将指示器附加到 `ViewPager2` 上。

!!! warning "attachToViewPager2"

    该方法被调用后将不再允许手动设置指示器数量和当前被选中的指示器。

```kotlin
binding.vp2indicator.attachToViewPager2(binding.vp2)
```

## 设置圆点指示器半径

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

调用 `setIndicatorCircleRadius` 设置圆形指示器半径。

```kotlin
binding.vp2indicator.setIndicatorCircleRadius(8f.DP)
```

<figure markdown>
  ![默认指示器大小](../img/default_size.jpg){ width="250" }
</figure>

<figure markdown>
  ![修改指示器大小](../img/change_size.jpg){ width="250" }
</figure>

## 设置圆点指示器颜色

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

当指示器的风格为 `Style.CIRCLE` ，可以通过 `setSelectedColor` 和 `setUnSelectedColor` 为指示器指定颜色。

```kotlin
binding.vp2indicator.apply {
    setSelectedColor(R.color.tomato)
    setUnSelectedColor(R.color.limegreen)
    ... // 其他设置
}
```

<figure markdown>
  ![修改指示器颜色](../img/change_color.jpg){ width="250" }
</figure>

## 设置指示器间距

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

可以通过 `indicator_item_distance` 或者调用 `setIndicatorItemDistance` 来修改指示器间距。

=== "Kotlin"

    ```kotlin
    binding.vp2indicator.setIndicatorItemDistance(10f.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.viewpager2.indicator.Vp2IndicatorView
        ...
        app:indicator_item_distance="10dp" />
    ```

## 设置指示器风格

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `indicator_style` 或者调用 `setIndicatorStyle` 来设置指示器类型，目前支持两种：

- CIRCLE：默认的圆形指示器
- BITMAP：指定对应的Bitmap为指示器形状

=== "Kotlin"

    ```kotlin
    binding.vp2indicator.setIndicatorStyle(Vp2IndicatorView.Style.CIRCLE)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.viewpager2.indicator.Vp2IndicatorView
        ...
        app:indicator_style="circle" />
    ```

## 设置 Bitmap 作为指示器

> 添加：[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

下面的示例为你展示了如何设置三角形 bitmap 为指示器。

```kotlin
binding.vp2indicator.apply {
    setIndicatorStyle(Style.BITMAP)
    setBitmapSize(20f.DP.toInt(), 20f.DP.toInt())
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
