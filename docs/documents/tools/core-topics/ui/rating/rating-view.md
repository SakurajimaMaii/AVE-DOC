# 评分控件

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/rating_view.mp4" type="video/mp4">
    </video>
</center>

## 快速使用

```xml
<com.ave.vastgui.tools.view.ratingview.RatingView
    android:id="@+id/ratingView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## 操作模式

> 添加：[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `star_touch_mode` 或者调用 `setStarTouchMode` 来设置星星的选中方式，目前支持三种：

- SLIDING：滑动
- CLICK：点击

    !!! 点击行为变更

        从 0.5.6 版本开始，当选择方式设置为 `Click` 时，星星的选中数量只能为整数。

- UNABLE：只能通过代码设置

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

## 设置排列方向

> 添加：[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

目前支持两种星星排列方式：

- HORIZONTAL：横向
- VERTICAL：纵向

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
 
## 设置星星间距

可以通过 `star_interval_width` 或者调用 `setStarIntervalWidth` 来设置星星的间距。

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

## 设置星星图片

对于选中的星星图片，可以通过 `star_selected` 或者调用 `setStarSelectedBitmap` 来设置。

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

对于未选中的星星图片，可以通过 `star_unselected` 和 `setStarUnselectedBitmap` 来设置。

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

## 设置星星图片大小

> 添加：[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

可以通过 `star_width` 和 `star_height` 或者调用 `setStarBitmapSize` 来设置星星的图片大小。

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

## 设置星星数量

可以通过 `star_count` 或者调用 `setStarCountNumber` 设置星星数量。

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

## 监听星星数量

> 添加：[:octicons-tag-24: Version 0.5.6](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#056)

通过 `setOnStarRatingChangeListener` 注册监听事件来观察评分的改变。

```kotlin
binding.ratingView.setOnStarRatingChangeListener(object : RatingView.OnStarRatingChangeListener {
    override fun onRatingChanged(rating: Float) {
        logger.d("当前星星评级为 $rating")
    }
})
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/RatingActivity.kt){ .md-button }
