# FragmentAdapter

`BaseFragmentStateAdapter` can facilitate you to quickly build a view pager2 suitable for [ViewPager2](https://developer.android.com/reference/kotlin/androidx/viewpager2/widget/ViewPager2).

## Get started

> Add:[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

```kotlin
private val fragments = ArrayList<Fragment>().apply {
    add(VideosFragment())
    add(ImagesFragment())
    add(ReceiverFragment())
    add(SenderFragment())
}

binding.vp2.adapter = BaseFragmentStateAdapter(this, fragments)
```
