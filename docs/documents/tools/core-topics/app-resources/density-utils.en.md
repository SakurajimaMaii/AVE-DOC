# Dimension

Click [Dimension](https://developer.android.google.cn/guide/topics/resources/more-resources?hl=zh-cn#Dimension) to get more information about dimension.

## PX to DP

```kotlin
val dpValue = DensityUtils.px2dp(10f)

val pxValue = DensityUtils.dp2px(10f)
```

## SP to PX

```kotlin
val spValue = DensityUtils.px2sp(10f)

val pxValue = DensityUtils.sp2px(10f)
```

## SP to DP

```kotlin
val spValue = DensityUtils.dp2sp(10f)

val dpValue = DensityUtils.sp2dp(10f)
```

## Get pixels with specified unit

```kotlin
val dpValue = 10f.DP
val spValue = 10f.SP
val pxValue = 10f.PX
val ptValue = 10f.PT
val mmValue = 10f.MM
val inValue = 10f.INCHES
```