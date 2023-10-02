# WaveProgressView

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

<figure markdown>
  ![WaveProgressView](../img/wave_progress_view.gif){ width="250" }
</figure>

## Quick start

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

```xml
<com.ave.vastgui.tools.view.progress.WaveProgressView
    android:id="@+id/waveProgressView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Custom background

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

!!! note "Stroke information"

    In the case of a custom background, your stroke settings will be invalid.

```xml
<com.ave.vastgui.tools.view.progress.WaveProgressView
    .... 
    android:background="@drawable/github" />
```

<figure markdown>
  ![Custom background](../img/wave_custom_background.jpg){ width="300" }
</figure>

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/view/WaveProgressViewActivity.kt){ .md-button }
