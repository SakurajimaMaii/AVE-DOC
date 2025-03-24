# MarqueeTextView

`MarqueeTextView` 重写了 `isFocused` 方法，以便你快速实现跑马灯功能。

<figure markdown>
  ![MarqueeTextView](../img/marquee-text-view.gif){ width="250" }
  <figcaption>MarqueeTextView</figcaption>
</figure>

## 快速使用

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

```xml
<com.ave.vastgui.tools.view.textview.MarqueeTextView
    android:id="@+id/marqueeTextView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="20dp"
    android:text="你好世界，你好世界，你好世界"
    android:textSize="30sp"/>
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/TextViewActivity.kt){ .md-button }
