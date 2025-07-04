# 面包屑

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

<center>
    <figure markdown>
        ![BreadCrumbLayout](./img/breadcrumb_layout.jpg){ width="540" }
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
        ![BreadCrumbLayout](./img/breadcrumb_layout.jpg){ width="540" }
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
        ![BreadCrumbLayout with red text](./img/breadcrumb_layout_text_color_red.jpg){ width="540" }
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
        ![BreadCrumbLayout with red text](./img/breadcrumb_layout_icon.jpg){ width="540" }
    </figure>
</center>

## 改变分隔符大小

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

可以通过 `breadcrumb_interval_icon_width` 和 `breadcrumb_interval_icon_height` 或者调用 `setIntervalIconSize` 来设置路径分隔符大小。

=== "Kotlin"

    ```kotlin
    binding.breadCrumbLayout.setIntervalIconSize(20f.DP, 20f.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.breadcrumb.BreadCrumbLayout
        ... 
        app:breadcrumb_interval_icon_height="20dp"
        app:breadcrumb_interval_icon_width="20dp" />
    ```

## 路径对象操作

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

```kotlin
// 添加单个路径对象
binding.breadCrumbLayout.addItem(BreadCrumb(path = "这是一个路径"))

// 添加多个路径对象
val items = arrayOf(BreadCrumb(drawable(R.drawable.ic_home_24dp)),
    BreadCrumb(drawable(R.drawable.ic_menu_24dp), "当这个页面标题很长很长很长时需要省略"),
    BreadCrumb("详情页"))
binding.breadCrumbLayout.addItems(items)
```

`addItem` 和 `addItems` 都会将路径对象的唯一 id 作为结果返回，可以通过此 id 移除指定的路径对象，例如：

```kotlin
val path = BreadCrumb(path = "这是一个路径")
val id = binding.breadCrumbLayout.addItem(path)
binding.breadCrumbLayout.removeLastItem(id)
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/BreadcrumbActivity.kt){ .md-button }
