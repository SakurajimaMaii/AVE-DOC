# ItemWrapper

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

[ItemWrapper](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter.base/-item-wrapper/index.html) 用于向适配器设置列表项的布局 id 以及设置列表项点击事件。

## 设置布局 id

### 直接设置：

[:octicons-tag-24: Version 1.2.0](https://ave.entropy2020.cn/version/VastAdapter/#111)

你可以在向适配器添加数据项时直接设置对应的布局 id ，例如：

```kotlin
mAdapter.add(readContacts(), R.layout.item_contact)
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AlphabetSideBarActivity.kt){ .md-button }

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

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/rvadapter/ImageActivity.kt){ .md-button }

### 列表项点击事件

[:octicons-tag-24: Version 1.1.1](https://ave.entropy2020.cn/version/VastAdapter/#111)

!!! warning "列表项点击事件说明"

    如果你为列表项单独定义了点击事件，那么它不再支持通用点击事件。

你可以借助 [ItemWrapper](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter.base/-item-wrapper/index.html) 为不同类型的列表项设置点击事件 ，例如：

```kotlin
// 定义点击事件
private val showDialog = OnItemClickListener<Images.Image> { view, _, _ ->
    MaterialAlertDialogBuilder(view.context).setMessage("这是一个点击事件").show()
}
private val showSnackBar = OnItemClickListener<Images.Image> { _, _, _ ->
    getSnackbar().setText("列表项被点击").show()
}

// 根据不同的 index 设置点击事件
if (0 == index % 2) {
    ItemWrapper(image, image.getLayoutId(), showDialog)
} else {
    ItemWrapper(image, image.getLayoutId(), showSnackBar)
}
```

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../../img/adapter_click_sample.mp4" type="video/mp4">
    </video>
</center>

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/rvadapter/ImageActivity.kt){ .md-button }

### 列表项内部控件点击事件

[:octicons-tag-24: Version 1.2.0](https://ave.entropy2020.cn/version/VastAdapter/#120)

你可以借助 [ItemWrapper](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter.base/-item-wrapper/index.html) 为列表项内部的控件添加点击事件，例如：

```kotlin
mAdapter.add(readContacts(), R.layout.item_contact) {
    addOnItemChildClickListener(R.id.name) { _, _, contact ->
        SimpleToast.showShortMsg("名字是 ${contact?.name}")
    }
    addOnItemChildClickListener(R.id.number) { _, _, contact ->
        SimpleToast.showShortMsg("电话号码是 ${contact?.number}")
    }
}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AlphabetSideBarActivity.kt){ .md-button }
