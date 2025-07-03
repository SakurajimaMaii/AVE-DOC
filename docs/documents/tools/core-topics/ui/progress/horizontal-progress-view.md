# HorizontalProgressView

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/horizontal_progress_view.mp4" type="video/mp4">
    </video>
</center>

## 快速使用

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

在示例图中，从上到下依次是 `HorizontalProgressView` ， `HorizontalTextProgressView` 和 `LineTextProgressView` 。

=== "HorizontalProgressView"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalProgressView
        android:layout_width="match_parent"
        android:layout_height="50dp" />
    ```

=== "HorizontalTextProgressView"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalTextProgressView
        android:layout_width="match_parent"
        android:layout_height="50dp" />
    ```

=== "LineTextProgressView"

    ```xml
    <com.ave.vastgui.tools.view.progress.LineTextProgressView
        android:layout_width="match_parent"
        android:layout_height="50dp" />
    ```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## HorizontalProgressView

### 自定义图片背景

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; 更新：[:octicons-clock-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

通过 `horizontal_progress_background_drawable` 和调用 `setProgressBkDrawable` 可以将图片设置为进度条背景。

=== "Kotlin"

    ```kotlin
    binding.horizontalProgressView.setProgressBkDrawable(R.drawable.background)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalProgressView
        ...
        app:horizontal_progress_background_drawable="@drawable/background" />
    ```

<figure markdown>
  ![Image background](../img/horizontal_background_drawable.jpg){ width="270" }
</figure>

### 自定义图片进度条

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; 更新：[:octicons-clock-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

通过 `horizontal_progress_drawable` 和调用 `setProgressDrawable` 可以将图片设置为进度条。

=== "Kotlin"

    ```kotlin
    binding.horizontalProgressView.setProgressDrawable(R.drawable.progress)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalProgressView
        ...
        app:horizontal_progress_drawable="@drawable/progress" />
    ```

<figure markdown>
  ![Image progress](../img/horizontal_progress_drawable.jpg){ width="270" }
</figure>

### 描边宽度

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

通过 `horizontal_progress_stroke_width` 和调用 `mStrokeWidth` 来设置进度条和边框的距离。

=== "Kotlin"

    ```kotlin
    binding.horizontalProgressView.strokeWidth = 0f
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalProgressView
        ...
        app:horizontal_progress_stroke_width="0dp" />
    ```

|                              Width 0dp                              |                              Width 5dp                              |
| :-----------------------------------------------------------------: | :-----------------------------------------------------------------: |
| ![Width 0dp](../img/horizontal_stroke_width_0dp.jpg){ width="270" } | ![Width 5dp](../img/horizontal_stroke_width_5dp.jpg){ width="270" } |

## HorizontalTextProgressView

### 进度条高度设置

> 添加：[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

进度条高度可以通过 `horizontal_text_progress_height` 和 `progressHeight` 来进行设置。

=== "Kotlin"

    ```kotlin
    binding.horizontalTextProgressView.progressHeight = 15f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalTextProgressView
        ...
        app:horizontal_text_progress_height="15dp" />
    ```

|                              Height 15dp                              |                              Height 25dp                              |
| :-------------------------------------------------------------------: | :-------------------------------------------------------------------: |
| ![Height 15dp](../img/horizontal_text_height_15dp.jpg){ width="270" } | ![Height 25dp](../img/horizontal_text_height_25dp.jpg){ width="270" } |

### 字体外边距

> 添加：[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

字体外边距可以通过 `horizontal_text_progress_text_margin` 和 `textMargin` 进行设置。

=== "Kotlin"

    ```kotlin
    binding.horizontalTextProgressView.textMargin = 10f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalTextProgressView
        ...
        app:horizontal_text_progress_text_margin="10dp" />
    ```

<figure markdown>
  ![Text margin](../img/horizontal_text_margin_10dp.jpg){ width="270" }
</figure>

### 文字框颜色设置

> 添加：[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

文字框颜色可以通过 `horizontal_text_progress_box_color` 和 `textBoxColor` 来进行设置。

=== "Kotlin"

    ```kotlin
    binding.horizontalTextProgressView.textBoxColor = ColorUtils.colorHex2Int("#e84118")
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.HorizontalTextProgressView
        ...
        app:horizontal_text_progress_box_color="#e84118" />
    ```

<figure markdown>
  ![Text margin](../img/horizontal_text_box_color.jpg){ width="270" }
</figure>

## LineTextProgressView

### 进度条高度设置

> 添加：[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

进度条高度可以通过 `linetext_progress_height` 和 `progressHeight` 来进行设置。

=== "Kotlin"

    ```kotlin
    binding.lineTextProgressView.progressHeight = 15f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.LineTextProgressView
        ...
        app:linetext_progress_height="15dp" />
    ```

|                           Height 15dp                           |                           Height 25dp                           |
| :-------------------------------------------------------------: | :-------------------------------------------------------------: |
| ![Height 15dp](../img/line_text_height_15dp.jpg){ width="270" } | ![Height 25dp](../img/line_text_height_25dp.jpg){ width="270" } |

### 字体外边距

> 添加：[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

字体外边距可以通过 `linetext_progress_text_margin` 和 `textMargin` 进行设置。

=== "Kotlin"

    ```kotlin
    binding.lineTextProgressView.textMargin = 10f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.LineTextProgressView
        ...
        app:linetext_progress_text_margin="10dp" />
    ```

<figure markdown>
  ![Text margin](../img/line_text_margin_10dp.jpg){ width="270" }
</figure>

### 文字框颜色设置

> 添加：[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

文字框颜色可以通过 `linetext_progress_box_color` 和 `textBoxColor` 来进行设置。

=== "Kotlin"

    ```kotlin
    binding.horizontalTextProgressView.textBoxColor = ColorUtils.colorHex2Int("#e84118")
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.LineTextProgressView
        ...
        app:linetext_progress_box_color="#e84118" />
    ```

<figure markdown>
  ![Text margin](../img/line_text_box_color.jpg){ width="270" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/HorizontalProgressViewActivity.kt){ .md-button }
