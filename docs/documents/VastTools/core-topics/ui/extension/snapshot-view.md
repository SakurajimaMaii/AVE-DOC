# 视图截屏

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

通过 `viewSnapshot` 可以将视图转为 [Bitmap](https://developer.android.com/reference/android/graphics/Bitmap) 进行保存。

## 对于已膨胀的视图

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

```kotlin
val bitmap = viewSnapshot(mBinding.snapshotWait)
```

## 对于未膨胀的视图

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

对于未膨胀的视图，你需要提供视图的 `width` 和 `height` 。

```kotlin
val view = LayoutInflater.from(this).inflate(R.layout.viewgroup_inflate, null, false)
val bitmap = viewSnapshot(view, SnapshotOption(1080, 540))
```
