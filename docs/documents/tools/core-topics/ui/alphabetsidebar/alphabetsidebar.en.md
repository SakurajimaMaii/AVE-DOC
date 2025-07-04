# AlphabetSideBar

[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/alphabetsidebar.mp4" type="video/mp4">
    </video>
</center>

## Quick start

[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

```xml
<com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
    android:id="@+id/alphabetsidebar"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## Location

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Background color can be set by  `alphabetsidebar_background` or calling `barBackgroundColor` .

=== "Kotlin"

    ```kotlin
    binding.alphabetsidebar.barBackgroundColor = ...
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Bar text size can be set by  `alphabetsidebar_text_size` or calling `barTextSize` .

=== "Kotlin"

    ```kotlin
    binding.alphabetsidebar.barTextSize = 20f.SP
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Bar text color can be set by `alphabetsidebar_text_color` or calling `barTextColor` .

=== "Kotlin"

    ```kotlin
    binding.alphabetsidebar.barTextColor = ...
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Indicator text color can be set by `alphabetsidebar_indicator_text_color` or calling `barIndicatorTextColor` .

The left is the default color, and the right is the modified color.

=== "Kotlin"

    ```kotlin
    binding.alphabetsidebar.barIndicatorTextColor = ...
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Bubble text size can be set by `alphabetsidebar_bubble_text_size` or calling `bubbleTextSize` .

The left is the default size and the right is the modified size.

=== "Kotlin"

    ```kotlin
    binding.alphabetsidebar.bubbleTextSize = 35f.SP
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Bubble text color can be set by `alphabetsidebar_bubble_text_color` or calling `bubbleTextColor` .

The left is the default color, and the right is the modified color.

=== "Kotlin"

    ```kotlin
    binding.alphabetsidebar.bubbleTextColor = ...
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

```kotlin
binding.alphabetsidebar.setLetterListener(object : AlphabetSideBar.LetterListener {
    override fun onIndicatorLetterUpdate(letter: String, index: Int, target: Int) {
        binding.recyclerView.smoothScrollToPosition(target)
    }
})
```

## Update indicator letter target index

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

By calling `setIndicatorLetterTargetIndex`, you can update the target index value of the letter, which will be stored in [AlphabetSp](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/kotlin/com/ave/vastgui/tools/view/alphabetsidebar/AlphabetSp.kt) . 

```kotlin
binding.alphabetsidebar.setIndicatorLetterTargetIndex("A", target)
```

Through the `onIndicatorLetterTargetUpdate` of `LetterListener` ,you can observe the update.

```kotlin
binding.alphabetsidebar.setLetterListener(object : AlphabetSideBar.LetterListener {
    ... // onIndicatorLetterUpdate implemention

    override fun onIndicatorLetterTargetUpdate(letter: String, target: Int) {
        logger.d(tag = "Gtest", "$letter target index is $target")
    }
})
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AlphabetSideBarActivity.kt){ .md-button }
