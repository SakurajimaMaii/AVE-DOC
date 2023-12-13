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

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Select method

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

Rating currently supports three select method：

- Sliding

    The rating can be set by sliding or calling `setStarRating` .

- Click

    !!! note "Click behavior changes"

        Starting from version 0.5.6, when the select method is set to `Click`, the selected number of stars can only be an integer.

    The rating can be set by clicking or calling `setStarRating` .

- Unable

    The rating can only be set by calling `setStarRating` .

=== "Kotlin"

    ```kotlin
    mBinding.ratingView.setStarSelectMethod(RatingSelectMethod.SLIDING)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_select_method="click" />
    ```

## Orientation

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

Rating currently supports two orientations：

- HORIZONTAL
- VERTICAL

=== "Kotlin"

    ```kotlin
    mBinding.ratingView.setStarOrientation(StarOrientation.HORIZONTAL)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.ratingview.RatingView
        ...
        app:star_orientation="horizontal" />
    ```

!!! note "StarOrientation.UNSPECIFIED"

    The default value of star orientation is `StarOrientation.UNSPECIFIED`, and the direction can only be modified once by calling `setStarOrientation` or `star_orientation`.
 
## Gap

```kotlin
mBinding.ratingView.setStarIntervalWidth(10F.DP)
```

## Image

The image of star can be set by `setStarSelectedBitmap` and `setStarUnselectedBitmap` .

```kotlin
mBinding.ratingView.apply{
    setStarSelectedBitmap(R.drawable.ic_star_normal)
    setStarUnselectedBitmap(R.drawable.ic_star_unselected)
}
```

## Size

The size of the star image can be set by `setStarBitMapSize` .

```kotlin
mBinding.ratingView.setStarBitMapSize(40F.DP,40F.DP)
```

## Number

The number of star can be set by `setStarCountNumber` .

```kotlin
mBinding.ratingView.setStarCountNumber(4)
```

## Listener

[:octicons-tag-24: Version 0.5.6](https://ave.entropy2020.cn/version/VastTools/#056)

Register a listener by calling `setOnStarRatingChangeListener` to observe the rating changes.

```kotlin
mBinding.ratingView.setOnStarRatingChangeListener(object : RatingView.OnStarRatingChangeListener {
    override fun onRatingChanged(rating: Float) {
        mLogger.d("Current rating is $rating")
    }
})
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/view/RatingActivity.kt){ .md-button }
