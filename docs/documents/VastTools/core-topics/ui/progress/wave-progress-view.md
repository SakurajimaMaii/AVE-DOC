# WaveProgressView

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

<figure markdown>
  ![波浪形进度条](../img/wave_progress_view.gif){ width="250" }
</figure>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

```xml
<com.ave.vastgui.tools.view.progress.WaveProgressView
    android:id="@+id/waveProgressView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 自定义背景

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

你可以指定 `BitmapDrawable` `VectorDrawable` 和 `VectorDrawableCompat` 类型的对象为背景。

!!! note "边框说明"

    在自定义背景的情况下，你对边框的设置会失效。

```xml
<com.ave.vastgui.tools.view.progress.WaveProgressView
    .... // 其他设置
    android:background="@drawable/github" />
```

<figure markdown>
  ![自定义背景](../img/wave_custom_background.jpg){ width="300" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/view/WaveProgressViewActivity.kt){ .md-button }
