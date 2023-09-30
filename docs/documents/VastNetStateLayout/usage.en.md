# Usage

## Xml

```xml
<com.ave.vastgui.netstatelayout.view.VastNetStateLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/net_state_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".activity.NetStateActivity">
    
    <!--Other content-->

</com.ave.vastgui.netstatelayout.view.VastNetStateLayout>
```

## Change page state

|     State     |       Method       |
| :-----------: | :----------------: |
|    Loading    |   showLoading()    |
| LoadingError  | showLoadingError() |
|   EmptyDate   |  showEmptyData()   |
| Network error |   showNetError()   |
|    Success    |   showSuccess()    |

## Set page event

### Network error event

```kotlin
val vastNetStateMgr = VastNetStateMgr(this)
    .setNetErrorListener {
        // Something to do when network error
    }
```

### Empty data event

```kotlin
val vastNetStateMgr = VastNetStateMgr(this)
    .setEmptyDataListener {
        // Something to do when empty data
    }
```

### Loading error event

```kotlin
val vastNetStateMgr = VastNetStateMgr(this)
    .setLoadingErrorListener {
        // Something to do when loading error
    }
```

### Loading event

```kotlin
val vastNetStateMgr = VastNetStateMgr(this)
    .setLoadingListener {
        // Something to do when loading
    }
```

## Config state background

`VastNetStateLayout` allows you to customize the state page. We take the custom network error page as an example:

```kotlin
vastNetStateMgr.setNetErrorView(R.layout.error_page)
```
