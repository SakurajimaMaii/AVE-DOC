# Snapshot view

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

`viewSnapshot` can convert the view into [Bitmap](https://developer.android.com/reference/android/graphics/Bitmap) for saving.

## For inflated views

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

```kotlin
val bitmap = viewSnapshot(mBinding.snapshotWait)
```

## For uninflated views

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

!!! note

    For uninflated views, you need to provide the `width` and `height` of the view by `SnapshotOption` .

```kotlin
val view = LayoutInflater.from(this).inflate(R.layout.viewgroup_inflate, null, false)
val bitmap = viewSnapshot(view, SnapshotOption(1080, 540))
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/extension/ViewSnapActivity.kt){ .md-button }
