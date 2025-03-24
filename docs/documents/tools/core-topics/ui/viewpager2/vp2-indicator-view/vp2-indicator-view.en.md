# Vp2IndicatorView

<figure markdown>
  ![Vp2IndicatorView](../img/vp2_indicator_view.gif){ width="250" }
</figure>

## Quick start

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

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## With ViewPager2

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Calling `attachToViewPager2` to attach to `ViewPager2` .

!!! warning "attachToViewPager2"

    After this method is called, it will no longer be allowed to manually set the number of indicators and the currently selected indicator.

```kotlin
mBinding.vp2indicator.attachToViewPager2(mBinding.vp2)
```

## Circle indicator radius

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Circle indicator radius can be set by `setIndicatorCircleRadius` .

```kotlin
mBinding.vp2indicator.setIndicatorCircleRadius(8F.DP)
```

<figure markdown>
  ![Default size](../img/default_size.jpg){ width="250" }
</figure>

<figure markdown>
  ![Change size](../img/change_size.jpg){ width="250" }
</figure>

## Circle indicator color

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Calling `setSelectedColor` and `setUnSelectedColor` to change the indicator color.

```kotlin
mBinding.vp2indicator.apply {
    setSelectedColor(R.color.tomato)
    setUnSelectedColor(R.color.limegreen)
    ... 
}
```

<figure markdown>
  ![Circle indicator color](../img/change_color.jpg){ width="250" }
</figure>

## Indicator gap

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

Calling `setIndicatorItemDistance` to change the gap distance.

```kotlin
mBinding.vp2indicator.setIndicatorItemDistance(10F.DP)
```

## Indicator style

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

Calling `setIndicatorStyle` to set the type, `Vp2IndicatorView` currently supports two types.

- CIRCLE
- BITMAP

## Indicator image

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```kotlin
mBinding.vp2indicator.apply {
    setIndicatorStyle(Vp2IndicatorType.BITMAP)
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
