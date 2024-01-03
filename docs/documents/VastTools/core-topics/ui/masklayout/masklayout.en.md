# MaskLayout

[:octicons-beaker-24: Version 0.5.6](https://ave.entropy2020.cn/version/VastTools/#056)

`MaskLayout` makes your theme switching more natural by adding animation.

!!! example "Experimental"

    Because the dark night switching mode adopted by each app is different, `MaskLayout` uses [ExperimentalView](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/kotlin/ com/ave/vastgui/tools/annotation/Experimental.kt) for annotation. Please consider whether to use it.

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/masklayout.mp4" type="video/mp4">
    </video>
</center>

## Quick start

[:octicons-beaker-24: Version 0.5.6](https://ave.entropy2020.cn/version/VastTools/#056)

```xml
<com.ave.vastgui.tools.view.masklayout.MaskLayout
    android:id="@+id/maskLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.ave.vastgui.app.activity.view.MaskLayoutActivity">

    ... // Other view

</com.ave.vastgui.tools.view.masklayout.MaskLayout>
```

## Animation styles

[:octicons-beaker-24: Version 0.5.6](https://ave.entropy2020.cn/version/VastTools/#056)

Currently, `MaskLayout` supports two styles of animation: `MaskAnimation.EXPANDED` and `MaskAnimation.COLLAPSED` .

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

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/MaskLayoutActivity.kt){ .md-button }
