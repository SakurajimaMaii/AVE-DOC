# 可绘制资源

## 设置单色背景

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

调用 `setSingle` 将 `GradientDrawable` 设置为单色。

```kotlin
getBinding().btn.background = GradientDrawable().apply {
    shape = RECTANGLE
    cornerRadius = 20f.DP
    setSingle(Color.argb(255,2,218,197))
}
```

<figure markdown>
  ![设置单色背景](../img/quick_start.jpg){ width="250" }
</figure>

## 设置圆角

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

调用 `setCornerRadii` 单独设置 `GradientDrawable` 的四个圆角。

```kotlin
// 设置四个圆角，半径均为50.0
getBinding().btn.background = GradientDrawable().apply {
    shape = RECTANGLE
    setSingle(Color.BLACK)
    cornerRadius = 50f
}

// 设置四个大小不同的圆角
getBinding().btn.background = GradientDrawable().apply {
    shape = RECTANGLE
    setSingle(Color.BLACK)
    setCornerRadii(0f, 0f, 50f, 50f)
}
```

<figure markdown>
  ![设置圆角](../img/set_corner_radius.jpg){ width="250" }
</figure>

## 设置渐变

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

`setGradient` 目前支持两种渐变颜色形式。

- startColor->endColor
- startColor->centerColor->endColor

```kotlin
// startColor->centerColor->endColor
getBinding().btn.background = GradientDrawable().apply {
    shape = RECTANGLE
    cornerRadius = 50f
    setGradient(
        45,
        colorHex2Int("#12c2e9"),
        colorHex2Int("#c471ed"),
        colorHex2Int("#f64f59")
    )
}

// startColor->endColor
getBinding().btn.background = GradientDrawable().apply {
    shape = RECTANGLE
    cornerRadius = 50f
    setGradient(
        45,
        colorHex2Int("#0F2027"),
        colorHex2Int("#78ffd6")
    )
}
```

<figure markdown>
  ![设置渐变](../img/set_gradient.jpg){ width="250" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/graphics/GradientDrawableActivity.kt){ .md-button }
