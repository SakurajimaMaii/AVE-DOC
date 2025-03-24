# 使用

## 快速开始

```xml
<com.ave.vastgui.netstatelayout.NetStateLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/net_state_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!--页面其他内容-->

</com.ave.vastgui.netstatelayout.NetStateLayout>
```

## 切换页面状态

`NetStateLayout` 为你提供了**五**种页面状态供你切换使用。

- 展示网络加载页面

    ```kotlin
    mNetStateLayout.showLoading()
    ```

- 展示空数据页面

    ```kotlin
    mNetStateLayout.showEmptyData()
    ```

- 展示网络加载错误页面

    [:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

    ```kotlin
    mNetStateLayout.showLoadingError()
    ```

    从 [1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111) 版本开始，可以将请求获取的代码和信息传给 `showLoadingError` 方法，例如：

    ```kotlin
    mNetStateLayout.showLoadingError(404, "目标地址不存在")
    ```

- 展示网络错误页面

    [:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

    ```kotlin
    mNetStateLayout.showNetError()
    ```

    从 [1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111) 版本开始，可以将请求获取的异常信息传给 `showNetError` 方法，例如：

    ```kotlin
    mNetStateLayout.showNetError(RuntimeException("网络不可用"))
    ```

- 当加载成功时，可以调用 `showSuccess` 来显示页面。

    ```kotlin
    mNetStateLayout.showSuccess()
    ```

## 更新页面

[:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

`NetStateLayout` 的 `OnXXXListener` 接口提供了 `onXXXInflate` 方法，在这里可以修改页面显示的内容，以修改默认页面 [default_empty_data](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastNetStateLayout/src/main/res/layout/default_empty_data.xml) 显示的信息为例：

```kotlin
val netStateMgr = NetStateMgr(this).apply {
    setOnEmptyDataListener(object : OnEmptyDataListener {
        override fun onEmptyDataInflate(view: View) {
            val textView: MaterialTextView =
                (view as ConstraintLayout).children.first() as MaterialTextView
            textView.text = "请求到的数据为空"
        }
    })
}
mNetStateLayout.setNetStateMgr(netStateMgr)
```

## 设置页面点击事件

[:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

`NetStateLayout` 的 `OnXXXListener` 接口提供了 `onXXXClick` 方法，在这里可以修改页面的点击事件，以网络不可用为例：

```kotlin
private val wifiSetting =
    registerForActivityResult(ActivityResultContracts.StartActivityForResult()) {
        ... 
    }

val netStateMgr = NetStateMgr(this).apply {
    setOnNetErrorListener(object : OnNetErrorListener {
        override fun onNetErrorClick() {
            wifiSetting.launch(Intent(Settings.ACTION_WIFI_SETTINGS))
        }
    })
}
mNetStateLayout.setNetStateMgr(netStateMgr)
```

## 自定义页面背景

`NetStateLayout` 允许你自定义状态页面，以自定义空数据页面为示例：

```kotlin
val netStateMgr = NetStateMgr(this).apply {
    setEmptyDataView(R.layout.page_empty_data_state)
}
mNetStateLayout.setNetStateMgr(netStateMgr)
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/NetStateLayoutActivity.kt){ .md-button }
