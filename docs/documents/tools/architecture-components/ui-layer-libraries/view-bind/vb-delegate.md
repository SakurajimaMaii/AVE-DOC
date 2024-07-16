# 视图绑定拓展

## 快速开始

### 在 Activity 中

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

```kotlin
private val mBindings by 
    viewBinding(ActivityWaveProgressViewBinding::inflate)
```

### 在 Fragment 中

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

调用 `public Fragment(@LayoutRes int contentLayoutId)` 来传入默认膨胀布局。

```kotlin
class VbFragment1 : Fragment(R.layout.fragment_sample) {

    private val mBinding by 
        viewBinding(FragmentSampleBinding::bind)

}
```

### 在 ViewHolder 中

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

```kotlin
class MyViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView) {
    private val binding by viewBinding(ItemPersonBinding::bind)
    val firstName = binding.firstName
    val lastName = binding.lastName
}
```

### 在 ViewGroup 中

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

需要调用 `public static View inflate(Context context, @LayoutRes int resource, ViewGroup root)` 方法来传入要膨胀的资源 id 。

```kotlin
class VbViewGroup1 @JvmOverloads constructor(context: Context, attrs: AttributeSet? = null) :
    LinearLayout(context, attrs) {

    private val binding by viewBinding(ViewgroupVbBinding::bind)

}
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/vbdelegate){ .md-button }
