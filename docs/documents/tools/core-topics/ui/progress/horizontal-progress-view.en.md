# HorizontalProgressView

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/horizontal_progress_view.mp4" type="video/mp4">
    </video>
</center>

## Quick start

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

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

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## HorizontalProgressView

### Drawable for background

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; Update:[:octicons-clock-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

Background can be set by `horizontal_progress_background_drawable` or calling `setProgressBkDrawable` .

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

### Drawable for progress

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; Update:[:octicons-clock-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

Progress can be set to the drawable by `horizontal_progress_drawable` or calling `setProgressDrawable` .

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

### Stroke

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Stroke of the progress can be set by `horizontal_progress_stroke_width` or calling `mStrokeWidth` .

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

|                                 Width 0dp                                  |                                 Width 5dp                                  |
| :------------------------------------------------------------------------: | :------------------------------------------------------------------------: |
| ![Image background](../img/horizontal_stroke_width_0dp.jpg){ width="270" } | ![Image background](../img/horizontal_stroke_width_5dp.jpg){ width="270" } |

## HorizontalTextProgressView

### Height of progress

> Add:[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

The height of progress can be set by  `horizontal_text_progress_height` or calling `progressHeight` .

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

### Text margin

> Add:[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Text margin can be set by `horizontal_text_progress_text_margin` or calling `textMargin` .

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

### Text box color

> Add:[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Color-int of the text box can be set by `horizontal_text_progress_box_color` or calling `textBoxColor` .

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

### Height of progress

> Add:[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

The height of progress can be set by `linetext_progress_height` or calling `progressHeight` .


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

### Text margin

> Add:[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Text margin can be set by `linetext_progress_text_margin` or calling `textMargin` .

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

### Text box color

> Add:[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Color-int of the text box can be set by `linetext_progress_box_color` or calling `textBoxColor` .

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

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/HorizontalProgressViewActivity.kt){ .md-button }
