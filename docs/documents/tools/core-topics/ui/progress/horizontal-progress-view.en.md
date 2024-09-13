# HorizontalProgressView

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/horizontal_progress_view.mp4" type="video/mp4">
    </video>
</center>

## Quick start

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

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

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## HorizontalProgressView

### Drawable for background

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

Background can be set by `horizontal_progress_background_drawable` or calling `setProgressBkDrawable` .
=== "Kotlin"

    ```kotlin
    mBinding.horizontalProgressView
        .setProgressBkDrawable(R.drawable.background)
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

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

Progress can be set to the drawable by `horizontal_progress_drawable` or calling `setProgressDrawable` .

=== "Kotlin"

    ```kotlin
    mBinding.horizontalProgressView
        .setProgressDrawable(R.drawable.progress)
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

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

Stroke of the progress can be set by `horizontal_progress_stroke_width` or calling `mStrokeWidth` .

=== "Kotlin"

    ```kotlin
    mBinding.horizontalProgressView
        .mStrokeWidth = 0f
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

[:octicons-tag-24: Version 0.5.5](https://ave.entropy2020.cn/version/tools/#055)

The height of progress can be set by  `horizontal_text_progress_height` or calling `setProgressHeight` .

!!! note "Minimum height of progress"

    The minimum height of progress will not smaller than the text height.

=== "Kotlin"

    ```kotlin
    mBinding.horizontalTextProgressView.mProgressHeight = 15f.DP
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

[:octicons-tag-24: Version 0.5.5](https://ave.entropy2020.cn/version/tools/#055)

Text margin can be set by `horizontal_text_progress_text_margin` or calling `mTextMargin` .

=== "Kotlin"

    ```kotlin
    mBinding.horizontalTextProgressView.mTextMargin = 10f.DP
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

Color-int of the text box can be set by `horizontal_text_progress_box_color` or calling `mTextBoxColor` .

=== "Kotlin"

    ```kotlin
    mBinding.horizontalTextProgressView.mTextBoxColor =
        ColorUtils.colorHex2Int("#e84118")
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

[:octicons-tag-24: Version 0.5.5](https://ave.entropy2020.cn/version/tools/#055)

The height of progress can be set by `linetext_progress_height` or calling `mProgressHeight` .


=== "Kotlin"

    ```kotlin
    mBinding.lineTextProgressView.mProgressHeight = 15f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.progress.LineTextProgressView
        ...
        app:linetext_progress_height="15dp" />
    ```

|                              Height 15dp                              |                              Height 25dp                              |
| :-------------------------------------------------------------------: | :-------------------------------------------------------------------: |
| ![Height 15dp](../img/line_text_height_15dp.jpg){ width="270" } | ![Height 25dp](../img/line_text_height_25dp.jpg){ width="270" } |

### Text margin

[:octicons-tag-24: Version 0.5.5](https://ave.entropy2020.cn/version/tools/#055)

Text margin can be set by `linetext_progress_text_margin` or calling `mTextMargin` .

=== "Kotlin"

    ```kotlin
    mBinding.lineTextProgressView.mTextMargin = 10f.DP
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

Color-int of the text box can be set by `linetext_progress_box_color` or calling `mTextBoxColor` .

=== "Kotlin"

    ```kotlin
    mBinding.horizontalTextProgressView.mTextBoxColor =
        ColorUtils.colorHex2Int("#e84118")
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
