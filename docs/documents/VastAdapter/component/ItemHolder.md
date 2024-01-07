# ItemHolder

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

当你使用 [VastAdapter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastAdapter/src/main/kotlin/com/ave/vastgui/adapter/VastAdapter.kt) ， [VastListAdapter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastAdapter/src/main/kotlin/com/ave/vastgui/adapter/VastListAdapter.kt) ， [VastPagingAdapter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastAdapter/src/main/kotlin/com/ave/vastgui/adapter/VastPagingAdapter.kt) 时，你需要继承 `ItemHolder` 并实现 `HolderFactory` 接口。以下为示例：

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

点击 [DefaultImageHolder](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/adapter/holder/ImageHolder.kt) 查看完整示例代码。

并将其作为参数传递给适配器，以下为示例：

```kotlin
private class ImageAdapter(context: Context) : 
    VastAdapter<Images.Image>(context, mutableListOf(DefaultImageHolder.Companion)) {

    ... // 其他代码

}
```
