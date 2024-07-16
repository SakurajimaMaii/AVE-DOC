# 滑动视图适配器

`VastFragmentAdapter` 可以方便你快速构建适合于 [ViewPager2](https://developer.android.com/reference/kotlin/androidx/viewpager2/widget/ViewPager2) 。

## 快速使用

你可以按照下列的方式将 `VastFragmentAdapter` 添加到你的 `Activity` 中:

```kotlin
mBinding.vp2.apply {
    adapter = VastFragmentAdapter(this@Vp2IndicatorActivity, ArrayList<Fragment>().apply {
        add(SampleVbVmFragment())
        add(SampleVmFragment())
        add(SampleVbFragment())
        add(SampleFragment())
    })
}
```
