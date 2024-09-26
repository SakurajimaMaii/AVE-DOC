# ViewBinding delegate

## Quick start

### Activity

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

```kotlin
private val mBindings by 
    viewBinding(ActivityWaveProgressViewBinding::inflate)
```

### Fragment

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

```kotlin
class VbFragment1 : Fragment(R.layout.fragment_sample) {

    private val mBinding by 
        viewBinding(FragmentSampleBinding::bind)

}
```

### ViewHolder

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

```kotlin
class MyViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView) {
    private val binding by viewBinding(ItemPersonBinding::bind)
    val firstName = binding.firstName
    val lastName = binding.lastName
}
```

### ViewGroup

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

```kotlin
class VbViewGroup1 @JvmOverloads constructor(context: Context, attrs: AttributeSet? = null) :
    LinearLayout(context, attrs) {

    private val binding by viewBinding(ViewgroupVbBinding::bind)

}
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/vbdelegate){ .md-button }
