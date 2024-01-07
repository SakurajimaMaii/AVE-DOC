# ItemDiffUtil

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

当你需要使用 [DiffUtil.ItemCallback](https://developer.android.com/reference/androidx/recyclerview/widget/DiffUtil.ItemCallback) 时，由于适配器直接存储的对象是 [ItemWrapper]() ，因而提供了 [ItemDiffUtil]() 来替代它。

```kotlin
object ImageDiffUtil : ItemDiffUtil<Images.Image>() {
    override fun newAreContentsTheSame(oldItem: Images.Image, newItem: Images.Image): Boolean {
        return oldItem.id == newItem.id
    }

    override fun newAreItemsTheSame(oldItem: Images.Image, newItem: Images.Image): Boolean {
        return oldItem.id == newItem.id
    }
}
```
