# Usage

## Quick start

```xml
<com.ave.vastgui.netstatelayout.NetStateLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/net_state_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!--content-->

</com.ave.vastgui.netstatelayout.NetStateLayout>
```

## Change page state

- Loading state

    ```kotlin
    mNetStateLayout.showLoading()
    ```

- Empty data state 

    ```kotlin
    mNetStateLayout.showEmptyData()
    ```

- Loading error state

    [:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

    ```kotlin
    mNetStateLayout.showLoadingError()
    ```

    Starting from version [1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111), you can set the response code and message to the `showLoadingError` , for example:

    ```kotlin
    mNetStateLayout.showLoadingError(404, "The address does not exist.")
    ```

- Net error state

    [:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

    ```kotlin
    mNetStateLayout.showNetError()
    ```

    Starting from version [1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111), you can set the requested exception to the `showNetError` , for example:

    ```kotlin
    mNetStateLayout.showNetError(RuntimeException("Network Unavailable"))
    ```

- When loading is successful, you can call `showSuccess` to display the page.

    ```kotlin
    mNetStateLayout.showSuccess()
    ```

## Update page content

[:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

The `OnXXXListener` of `NetStateLayout` provides the `onXXXInflate` method, where you can modify the content displayed on the page. Take modifying the information displayed on the default page [default_empty_data](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastNetStateLayout/src/main/res/layout/default_empty_data.xml) as an example:

```kotlin
val netStateMgr = NetStateMgr(this).apply {
    setOnEmptyDataListener(object : OnEmptyDataListener {
        override fun onEmptyDataInflate(view: View) {
            val textView: MaterialTextView =
                (view as ConstraintLayout).children.first() as MaterialTextView
            textView.text = "The response data is empty"
        }
    })
}
mNetStateLayout.setNetStateMgr(netStateMgr)
```

## Set page click event

[:octicons-tag-24: Version 1.1.1](https://sakurajimamaii.github.io/AVE-DOC/version/VastNetStateLayout/#111)

The `OnXXXListener` interface of `NetStateLayout` provides the `onXXXClick` , where you can modify the click event of the page. Take the network unavailability as an example:

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

## Customize state page

`NetStateLayout` allows you to customize the state page. Take a custom empty data page as an example:

```kotlin
val netStateMgr = NetStateMgr(this).apply {
    setEmptyDataView(R.layout.page_empty_data_state)
}
mNetStateLayout.setNetStateMgr(netStateMgr)
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/NetStateLayoutActivity.kt){ .md-button }
