# AlphabetSideBar

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/alphabetsidebar.mp4" type="video/mp4">
    </video>
</center>

## Quick start

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

```xml
<com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
    android:id="@+id/alphabetsidebar"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Location

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Currently supports **left** and **right** . It can be set by `alphabetsidebar_location` or calling `setLocation`.

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.setLocation(AlphabetSideBar.LEFT)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_location="left" />
    ```

<center>
![Location left](../img/location_left.jpg){ width="220" }
![Location right](../img/location_right.jpg){ width="220" }
</center>

## Background color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Background color can be set by  `alphabetsidebar_background` or calling `mBackgroundColor` .

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.mBackgroundColor = ...
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_background="#26B2BEC3" />
    ```

<center>
![Background](../img/background.jpg){ width="220" }
</center>

## Bar text size

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Bar text size can be set by  `alphabetsidebar_text_size` or calling `mBarTextSize` .

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.mBarTextSize = 20f.SP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_text_size="20sp" />
    ```

<center>
![Text size](../img/text_size.jpg){ width="220" }
</center>

## Bar text color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Bar text color can be set by `alphabetsidebar_text_color` or calling `mBarTextColor` .

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.mBarTextColor = ...
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_text_color="#e17055" />
    ```

<center>
![Text color](../img/text_color.jpg){ width="220" }
</center>

## Indicator text color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Indicator text color can be set by `alphabetsidebar_indicator_text_color` or calling `mBarIndicatorTextColor` .

The left is the default color, and the right is the modified color.

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.mBarIndicatorTextColor = ...
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_indicator_text_color="#0984e3" />
    ```

<center>
![Indicator text default color](../img/indicator_text_default_color.jpg){ width="150" }
![Indicator text color](../img/indicator_text_color.jpg){ width="150" }
</center>

## Bubble text size

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Bubble text size can be set by `alphabetsidebar_bubble_text_size` or calling `mBubbleTextSize` .

The left is the default size and the right is the modified size.

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.mBubbleTextSize = 35f.SP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_bubble_text_size="35sp" />
    ```

<center>
![Bubble text default size](../img/bubble_text_default_size.jpg){ width="270" }
![Bubble text size](../img/bubble_text_size.jpg){ width="270" }
</center>

## Bubble text color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

Bubble text color can be set by `alphabetsidebar_bubble_text_color` or calling `mBubbleTextColor` .

The left is the default color, and the right is the modified color.

=== "Kotlin"

    ```kotlin
    mBinding.alphabetsidebar.mBubbleTextColor = ...
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
        ...
        app:alphabetsidebar_bubble_text_color="#4a69bd" />
    ```

<center>
![Bubble text default color](../img/bubble_text_default_color.jpg){ width="270" }
![Bubble text default color](../img/bubble_text_color.jpg){ width="270" }
</center>

## Register listener

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

```kotlin
mBinding.alphabetsidebar.setLetterListener(object : AlphabetSideBar.LetterListener {
    override fun onIndicatorLetterUpdate(letter: String, index: Int, target: Int) {
        mBinding.recyclerView.smoothScrollToPosition(target)
    }
})
```

## Update indicator letter target index

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

By calling `setIndicatorLetterTargetIndex`, you can update the target index value of the letter, which will be stored in [AlphabetSp](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/view/alphabetsidebar/AlphabetSp.kt) . 

```kotlin
mBinding.alphabetsidebar.setIndicatorLetterTargetIndex("A", target)
```

Through the `onIndicatorLetterTargetUpdate` of `LetterListener` ,you can observe the update.

```kotlin
mBinding.alphabetsidebar.setLetterListener(object : AlphabetSideBar.LetterListener {
    ... // onIndicatorLetterUpdate implemention

    override fun onIndicatorLetterTargetUpdate(letter: String, target: Int) {
        mLogger.d(tag = "Gtest", "$letter target index is $target")
    }
})
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AlphabetSideBarActivity.kt){ .md-button }
