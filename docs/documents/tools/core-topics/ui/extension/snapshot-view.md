# 视图截屏

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

通过 `viewSnapshot` 可以将视图转为 [Bitmap](https://developer.android.com/reference/android/graphics/Bitmap) 进行保存。

## 对于已膨胀的视图

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

```kotlin
val bitmap = viewSnapshot(mBinding.snapshotWait)
```

## 对于未膨胀的视图

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

!!! note "SnapshotOption"

    对于未膨胀的视图，你需要通过 `SnapshotOption` 提供视图的 `width` 和 `height` 。

```kotlin
val view = LayoutInflater.from(this).inflate(R.layout.viewgroup_inflate, null, false)
val bitmap = viewSnapshot(view, SnapshotOption(1080, 540))
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/extension/ViewSnapActivity.kt){ .md-button }
