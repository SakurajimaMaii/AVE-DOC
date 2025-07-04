# Vp2IndicatorView

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<figure markdown>
  ![Vp2IndicatorView](../img/vp2_indicator_view.gif){ width="250" }
</figure>

## Quick start

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

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

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Attach to ViewPager2

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Calling `attachToViewPager2` to attach to `ViewPager2` .

!!! warning "attachToViewPager2"

    After `attachToViewPager2()` is called, it will no longer be allowed to set the count of indicators and the current index of indicator.

```kotlin
binding.vp2indicator.attachToViewPager2(binding.vp2)
```

## Radius of indicator

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

When the style of the indicator is `Style.CIRCLE` , the radius of indicator can be set by calling `setIndicatorCircleRadius` .

```kotlin
binding.vp2indicator.setIndicatorCircleRadius(8f.DP)
```

<figure markdown>
  ![Default size](../img/default_size.jpg){ width="250" }
</figure>

<figure markdown>
  ![Change size](../img/change_size.jpg){ width="250" }
</figure>

## Color of indicator

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

When the style of the indicator is `Style.CIRCLE` , the color of the indicator can be set by calling `setSelectedColor` and `setUnSelectedColor` .

```kotlin
binding.vp2indicator.apply {
    setSelectedColor(R.color.tomato)
    setUnSelectedColor(R.color.limegreen)
    ... 
}
```

<figure markdown>
  ![Circle indicator color](../img/change_color.jpg){ width="250" }
</figure>

## Interval width of indicator

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

The interval width of indicator can be set by `indicator_item_distance` or calling `setIndicatorItemDistance` to change the gap distance.

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

## Style of indicator

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

The indicator style can be set by `setIndicatorStyle` or calling `setIndicatorStyle` , `Vp2IndicatorView` currently supports two types:

- CIRCLE
- BITMAP

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

## Bitmap of indicator

> Add:[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```kotlin
binding.vp2indicator.apply {
    setIndicatorStyle(Style.BITMAP)
    setBitmapSize(20f.DP.toInt(),20f.DP.toInt())
    setSelectedBitmap(R.drawable.ic_indicator_select)
    setUnSelectedBitmap(R.drawable.ic_indicator_unselect)
    ... 
}
```

<figure markdown>
  ![bitmap](../img/bitmap.jpg){ width="250" }
</figure>

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/Vp2IndicatorActivity.kt){ .md-button }
