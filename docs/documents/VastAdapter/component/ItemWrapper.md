# ItemWrapper

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

[ItemWrapper]() 用于向适配器设置列表项的布局 id 以及设置列表项点击事件。

## 设置布局 id

### 直接设置：

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

你可以在向适配器添加数据项时直接设置对应的布局 id ，例如：

```kotlin
fun addContact(name: String, number: String) {
    val index = itemCount
    mDataSource.add(index, ItemWrapper(Contact(name, number), layoutId = R.layout.item_contact))
    notifyItemChanged(index)
}
```

点击 [ContactAdapter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/adapter/ContactAdapter.kt) 查看完整示例。

### 根据条件进行设置:

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

如果你需要根据不同的数据类型指定不同的布局，你可以在向适配器添加数据项时采取下面的方法：

```kotlin
// 数据项定义
data class Images(...) : ResponseApi {
    data class Image(val type: String, ...) {
        fun getLayoutId() = 
            if (id % 2 == 0) R.layout.item_image_comic else R.layout.item_image_default
    }
}

fun addTypeImage(image: Images.Image) {
    val index = itemCount
    mDataSource.add(index, ItemWrapper(image, layoutId = image.getLayoutId()))
    notifyItemChanged(index)
}
```

点击 [ImageAdapter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/adapter/ImageAdapter.kt) 查看完整示例。

## 设置点击事件

### 通用点击事件

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

如果你想要为列表项设置通用点击事件，通常只需要进行以下操作：

```kotlin
mImageAdapter.apply {
    setOnItemClickListener { _, pos, _ ->
        showShortMsg("Click event and pos is $pos.")
    }
    setOnItemLongClickListener { _, pos, _ ->
        showShortMsg("Long click event and pos is $pos.")
        true
    }
}
```

点击 [ImageActivity](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/rvadapter/ImageActivity.kt) 查看完整示例。

### 列表项点击事件

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

!!! warning "列表项点击事件说明"

    如果你为列表项单独定义了点击事件，那么它不再支持通用点击事件。

你可以借助 [ItemWrapper]() 为不同类型的列表项设置点击事件 ，例如：

```kotlin
// 定义点击事件
private val sampleClick1 = OnItemClickListener<Images.Image> { view, _, _ ->
    MaterialAlertDialogBuilder(view.context).setTitle("这是一个点击事件。").show()
}
private val sampleClick2 = OnItemClickListener<Images.Image> { _, _, _ ->
    getSnackbar().setText("列表项被点击").show()
}

// 根据不同的 index 设置点击事件
if (0 == index % 2) {
    ItemWrapper(image, image.getLayoutId(), sampleClick1)
} else {
    ItemWrapper(image, image.getLayoutId(), sampleClick2)
}
```

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../../img/adapter_click_sample.mp4" type="video/mp4">
    </video>
</center>

点击 [ImageActivity](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/rvadapter/ImageActivity.kt) 查看完整示例。

### 列表项内部控件点击事件

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

你可以借助 [ItemWrapper]() 为列表项内部的控件添加点击事件，例如：

```kotlin
inline fun addContact(..., scope: ItemWrapper<Contact>.() -> Unit) {
    val index = itemCount
    val wrapper = ItemWrapper(...).also(scope)
    getDataSource().add(index, wrapper)
    notifyItemChanged(index)
}

mAdapter.addContact(...) {
    addOnItemChildClickListener(R.id.name) { _, _, _ ->
        SimpleToast.showShortMsg("名字是 $name")
    }
    addOnItemChildClickListener(R.id.number) { _, _, _ ->
        SimpleToast.showShortMsg("电话号码是 $number")
    }
}
```

点击 [ContactAdapter](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/adapter/ContactAdapter.kt) 查看完整示例。
