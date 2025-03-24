# WaveProgressView

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/wave_progress_view.mp4" type="video/mp4">
    </video>
</center>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

```xml
<com.ave.vastgui.tools.view.progress.WaveProgressView
    android:id="@+id/waveProgressView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 自定义背景

[:octicons-tag-24: Version 0.5.5](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#055)

你可以指定 `BitmapDrawable` `VectorDrawable` 和 `VectorDrawableCompat` 类型的对象为背景。

!!! note "边框说明"

    在自定义背景的情况下，你对边框的设置会失效。

```xml
<com.ave.vastgui.tools.view.progress.WaveProgressView
    .... // 其他设置
    app:wave_progress_image="@drawable/github" />
```

<figure markdown>
  ![自定义背景](../img/wave_custom_background.jpg){ width="300" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/WaveProgressViewActivity.kt){ .md-button }
