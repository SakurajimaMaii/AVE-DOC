# 面包屑

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

<center>
    <figure markdown>
    ![BreadCrumbLayout](../img/breadcrumb_layout.jpg){ width="540" }
    </figure>
</center>

## 路径对象

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

目前支持三种路径对象，以下是示例：

```kotlin
// 仅图标
BreadCrumb(drawable(R.drawable.ic_home_24dp))
// 图标+文字
BreadCrumb(drawable(R.drawable.ic_menu_24dp), "当这个页面标题很长很长很长时需要省略")
// 仅文字
BreadCrumb("详情页")
```

效果如下图所示：

<center>
    <figure markdown>
        ![BreadCrumbLayout](../img/breadcrumb_layout.jpg){ width="540" }
    </figure>
</center>

## 设置路径文字颜色 

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `breadcrumb_text_color` 或者调用 `setTextColor` 来设置路径文字的颜色。

=== "Kotlin"

    ```kotlin
    binding.breadCrumbLayout.setTextColor(Color.RED)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.breadcrumb.BreadCrumbLayout
        ... 
        app:breadcrumb_text_color="@color/red" />
    ```

<center>
    <figure markdown>
        ![BreadCrumbLayout with red text](../img/breadcrumb_layout_text_color_red.jpg){ width="540" }
    </figure>
</center>

## 设置路径文字大小

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `breadcrumb_text_size` 或者调用 `setTextSize` 来设置路径文字的颜色。

=== "Kotlin"

    ```kotlin
    binding.breadCrumbLayout.setTextSize(16f.SP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.breadcrumb.BreadCrumbLayout
        ... 
        app:breadcrumb_text_size="16sp" />
    ```

## 切换分隔符

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `breadcrumb_interval_icon` 或者调用 `setIntervalIcon` 来设置路径分隔符。

=== "Kotlin"

    ```kotlin
    binding.breadCrumbLayout.setIntervalIcon(R.drawable.ic_breadcrumb_interval_icon_32dp)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.breadcrumb.BreadCrumbLayout
        ... 
        app:breadcrumb_interval_icon="@drawable/ic_breadcrumb_default_interval_icon" />
    ```

<center>
    <figure markdown>
        ![BreadCrumbLayout with red text](../img/breadcrumb_layout_icon.jpg){ width="540" }
    </figure>
</center>

## 添加路径对象

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `addItem` 和 `addItems` 来添加路径对象，以下是示例：

```kotlin
binding.breadCrumbLayout.addItem(BreadCrumb(path = "这是一个路径"))
```
