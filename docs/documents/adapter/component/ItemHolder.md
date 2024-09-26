# ItemHolder

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

当你使用 [BaseAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-adapter/index.html) ， [BaseListAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-list-adapter/index.html) ， [BasePagingAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-paging-adapter/index.html) 时，你需要继承 [ItemHolder](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter.base/-item-holder/index.html) 并实现 [HolderFactory](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter.base/-item-holder/-holder-factory/index.html) 接口。以下为示例：

```kotlin
class DefaultImageHolder(itemView: View) : ItemHolder<Images.Image>(itemView) {
    private val image: ShapeableImageView = itemView.findViewById(R.id.iidImage)
    private val title: MaterialTextView = itemView.findViewById(R.id.iidTitle)

    override fun onBindData(item: Images.Image) {
        image.load(item.url) {
            crossfade(true)
            placeholder(R.drawable.background)
        }
        title.text = item.title
    }

    companion object : HolderFactory<Images.Image> {
        override fun onCreateHolder(parent: ViewGroup, viewType: Int): DefaultImageHolder {
            val view =
                LayoutInflater.from(parent.context).inflate(layoutId, parent, false)
            return DefaultImageHolder(view)
        }

        override val layoutId: Int
            get() = R.layout.item_image_default
    }
}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/adapter/holder/ImageHolder.kt){ .md-button }

并将其作为参数传递给适配器，以下为示例：

```kotlin
private class ImageAdapter(context: Context) : 
    BaseAdapter<Images.Image>(context, mutableListOf(DefaultImageHolder.Companion)) {

    ... // 其他代码

}
```
