# Rating

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/rating_view.mp4" type="video/mp4">
    </video>
</center>

## Quick start

```xml
<com.ave.vastgui.tools.view.ratingview.RatingView
    android:id="@+id/ratingView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## Mode

> Add:[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Rating currently supports three select method：

- SLIDING

    The rating can be set by sliding or calling `setStarRating` .

- CLICK

    !!! note "Click behavior changes"

        Starting from version 0.5.6, when the select method is set to `Click`, the selected number of stars can only be an integer.

    The rating can be set by clicking or calling `setStarRating` .

- UNABLE

    The rating can only be set by calling `setStarRating` .

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarTouchMode(RatingView.Mode.SLIDING)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_touch_mode="click" />
    ```

## Orientation

> Add:[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Rating currently supports two orientations：

- HORIZONTAL
- VERTICAL

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarOrientation(RatingView.Orientation.HORIZONTAL)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_orientation="horizontal" />
    ```
 
## Interval width

The interval width between stars can be set by  `star_interval_width` or calling `setStarIntervalWidth` .

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarIntervalWidth(10f.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_interval_width="10dp" />
    ```

## Image

For selected star images, it can be set by `star_selected` or calling `setStarSelectedBitmap` . 

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarSelectedBitmap(R.drawable.ic_star_normal)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_selected="@drawable/ic_star_selected" />
    ```

For unselected star images, it can be set by `star_unselected` and `setStarUnselectedBitmap` .

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarUnselectedBitmap(R.drawable.ic_star_unselected)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_unselected="@drawable/ic_star_unselected" />
    ```

## Size

> Add:[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

The size of the star image can be set by `star_width` and `star_height` or calling `setStarBitmapSize` .

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarBitmapSize(40F.DP, 40F.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_width="40dp"
        app:star_height="40dp" />
    ```

## Number

The number of star can be set by `star_count` or calling `setStarCountNumber` .

=== "Kotlin"

    ```kotlin
    binding.ratingView.setStarCountNumber(4)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_count="5" />
    ```

## Listener

> Add:[:octicons-tag-24: Version 0.5.6](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#056)

Register a listener by calling `setOnStarRatingChangeListener` to observe the rating changes.

```kotlin
binding.ratingView.setOnStarRatingChangeListener(object : RatingView.OnStarRatingChangeListener {
    override fun onRatingChanged(rating: Float) {
        logger.d("Current rating is $rating")
    }
})
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/RatingActivity.kt){ .md-button }
