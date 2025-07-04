# 滑动视图适配器

`BaseFragmentStateAdapter` 可以方便你快速构建适合于 [ViewPager2](https://developer.android.com/reference/kotlin/androidx/viewpager2/widget/ViewPager2) 。

## 快速使用

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

```kotlin
private val fragments = ArrayList<Fragment>().apply {
    add(VideosFragment())
    add(ImagesFragment())
    add(ReceiverFragment())
    add(SenderFragment())
}

binding.vp2.adapter = BaseFragmentStateAdapter(this, fragments)
```
