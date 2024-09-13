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

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 设置选中方式

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/tools/#053)

调用 `setStarSelectMethod` 来设置星星的选中方式，目前支持三种：

- Sliding：滑动
- Click：点击

    !!! 点击行为变更

        从 0.5.6 版本开始，当选择方式设置为 `Click` 时，星星的选中数量只能为整数。

- Unable：只能通过代码设置

```kotlin
mBinding.ratingView.setStarSelectMethod(RatingSelectMethod.SLIDING)
```

## 设置排列方向

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/tools/#053)

目前支持两种星星排列方式：

- HORIZONTAL：横向
- VERTICAL：纵向

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

!!! note "默认排列方向"

    星星的默认排列方向为 `StarOrientation.UNSPECIFIED` ，方向仅允许通过 `setStarOrientation` 或 `star_orientation` 修改一次。
 
## 设置星星间距

调用 `setStarIntervalWidth` 来设置星星的间距

```kotlin
mBinding.ratingView.setStarIntervalWidth(10F.DP)
```

## 设置星星图片

调用 `setStarSelectedBitmap` 和 `setStarNormalBitmap` 来设置星星图片。

```kotlin
mBinding.ratingView.apply{
    setStarSelectedBitmap(R.drawable.ic_star_normal)
    setStarUnselectedBitmap(R.drawable.ic_star_unselected)
}
```

## 设置星星图片大小

调用 `setStarBitMapSize` 来设置星星图片大小

```kotlin
mBinding.ratingView.setStarBitMapSize(40F.DP,40F.DP)
```

## 设置星星数量

调用 `setStarCountNumber` 设置星星数量

```kotlin
mBinding.ratingView.setStarCountNumber(4)
```

## 监听星星数量

[:octicons-tag-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

通过 `setOnStarRatingChangeListener` 注册监听事件来观察评分的改变。

```kotlin
mBinding.ratingView.setOnStarRatingChangeListener(object : RatingView.OnStarRatingChangeListener {
    override fun onRatingChanged(rating: Float) {
        mLogger.d("当前星星评级为 $rating")
    }
})
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/RatingActivity.kt){ .md-button }
