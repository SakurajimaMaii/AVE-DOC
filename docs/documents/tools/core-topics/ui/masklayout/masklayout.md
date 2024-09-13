# 遮罩布局

[:octicons-beaker-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

遮罩布局通过添加动画的形式来使你的主题切换变得更加自然。

!!! example "试验性说明"

    因为每个 app 所采取的暗夜切换模式不同，因此该组件使用 [ExperimentalView](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/annotation/Experimental.kt) 进行标注。请你酌情考虑是否使用。

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/masklayout.mp4" type="video/mp4">
    </video>
</center>

## 快速使用

[:octicons-beaker-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

```xml
<com.ave.vastgui.tools.view.masklayout.MaskLayout
    android:id="@+id/maskLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.ave.vastgui.app.activity.view.MaskLayoutActivity">

    ... // 布局内其他控件

</com.ave.vastgui.tools.view.masklayout.MaskLayout>
```

## 动画类型

[:octicons-beaker-24: Version 0.5.6](https://ave.entropy2020.cn/version/tools/#056)

目前，遮罩布局支持延展 `MaskAnimation.EXPANDED` 和收缩 `MaskAnimation.COLLAPSED` 两种形式的动画。

- MaskAnimation.EXPANDED

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/masklayout.mp4" type="video/mp4">
    </video>
</center>

- MaskAnimation.COLLAPSED

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/masklayout_collapsed.mp4" type="video/mp4">
    </video>
</center>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/MaskLayoutActivity.kt){ .md-button }
