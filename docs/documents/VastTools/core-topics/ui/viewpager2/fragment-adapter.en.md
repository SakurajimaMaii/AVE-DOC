# FragmentAdapter

`VastFragmentAdapter` can facilitate you to quickly build a view pager2 suitable for [ViewPager2](https://developer.android.com/reference/kotlin/androidx/viewpager2/widget/ViewPager2).

## Get started

You can add `VastFragmentAdapter` to your `Activity` in the following way:

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
