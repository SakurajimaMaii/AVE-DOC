# 字母索引栏

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/alphabetsidebar.mp4" type="video/mp4">
    </video>
</center>

## 快速使用

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

```xml
<com.ave.vastgui.tools.view.alphabetsidebar.AlphabetSideBar
    android:id="@+id/alphabetsidebar"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 索引栏位置

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

索引栏目前支持 **左边** 和 **右边** 两种模式。可以通过 `alphabetsidebar_location` 和调用 `setLocation` 来进行设置。

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

## 背景颜色

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `alphabetsidebar_background` 和调用 `mBackgroundColor` 来设置背景颜色。

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

## 索引栏字体大小

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `alphabetsidebar_text_size` 和调用 `mBarTextSize` 来设置索引栏字体大小。

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

## 索引栏字体颜色

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `alphabetsidebar_text_color` 和调用 `mBarTextColor` 来设置索引栏字体颜色。

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
![Text_color](../img/text_color.jpg){ width="220" }
</center>

## 当前索引字体颜色

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `alphabetsidebar_indicator_text_color` 和调用 `mBarIndicatorTextColor` 来设置当前索引字体颜色。

左边是默认颜色，右边是修改后的颜色。

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

## 气泡内文字大小

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `alphabetsidebar_bubble_text_size` 和调用 `mBubbleTextSize` 来设置气泡内文字大小。

左边是默认大小，右边是修改后的大小。

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

## 气泡内文字颜色

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `alphabetsidebar_bubble_text_color` 和调用 `mBubbleTextColor` 来设置气泡内文字颜色。

左边是默认颜色，右边是修改后的颜色。

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

## 注册监听事件

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

通过 `setLetterListener` 方法注册监听事件。

```kotlin
mBinding.alphabetsidebar.setLetterListener(object : AlphabetSideBar.LetterListener {
    override fun onIndicatorLetterUpdate(letter: String, index: Int, target: Int) {
        mBinding.recyclerView.smoothScrollToPosition(target)
    }
})
```

## 更新字母目标索引

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

通过调用 `setIndicatorLetterTargetIndex` ，你可以更新字母的目标索引值，该索引值会被存储在 [AlphabetSp](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/view/alphabetsidebar/AlphabetSp.kt) 中。

```kotlin
mBinding.alphabetsidebar.setIndicatorLetterTargetIndex("A", target)
```

你可以通过 `LetterListener` 的 `onIndicatorLetterTargetUpdate` 方法监听目标索引的更新。

```kotlin
mBinding.alphabetsidebar.setLetterListener(object : AlphabetSideBar.LetterListener {
    ... // onIndicatorLetterUpdate 实现

    override fun onIndicatorLetterTargetUpdate(letter: String, target: Int) {
        mLogger.d(tag = "Gtest", "$letter 目标索引更新为 $target")
    }
})
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AlphabetSideBarActivity.kt){ .md-button }
