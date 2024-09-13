# AppendableStyleScope

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

`appendableStyleScope` 允许你快速构建多种样式文字。

<figure markdown>
  ![AppendableStyleScope](../img/appendable_style_scope.jpg){ width="400" }
  <figcaption>AppendableStyleScope</figcaption>
</figure>

## Quick start

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

The following example shows how to create a link text.

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(url = "https://www.baidu.com/")) {
        append("这是一个链接")
    }
}
```
The following example shows how to create a image text.

```kotlin
appendableStyleScope(getBinding().tv) {
    withImage(ImageSpan(this, R.mipmap.ic_launcher))
}
```

The following example shows you how to create a complex rich text format**(RTF)** string.

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(QuoteSpan(ColorUtils.colorHex2Int("#27ae60"), 10, 30))) {
        withStyle(AppendableStyle(fontSize = 20F.SP.toInt())) {
            appendLine("什么是 Android?")
        }
        append("一个颠覆移动设备功能的平台，你可以访问")
        withStyle(AppendableStyle("https://www.android.com/intl/zh-CN_cn/what-is-android/")) {
            append("链接")
        }
        appendLine("来了解更多。")
        append(
            "从只能让设备运行，到让生活更轻松，都是Android在背后提供强力支持。" +
                    "有了Android, 才能让GPS避开拥堵，用手表发短信，让Google助理回答问题。" +
                    "目前有 25 亿部活跃设备搭载了 Android 操作系统。Android 能够为各种设备" +
                    "提供强力支持，从 5G 手机到炫酷的平板电脑，不胜枚举。"
        )
        withStyle(AppendableStyle(ScriptMode.SUPERSCRIPT)) { append("[1]") }
        append("\n")
        withImage(ImageSpan(this@DateActivity, R.drawable.android_logo))
    }
}
```

<figure markdown>
  ![AppendableStyleScope](../img/appendable_style_scope.jpg){ width="400" }
  <figcaption>AppendableStyleScope</figcaption>
</figure>

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/text/AppendableStyleActivity.kt){ .md-button }

## Common style

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

- foreColor: text color.
- backColor: Text background color.
- fontStyle: text style, currently supports bold, italic or normal.
- fontFamily: text font.
- fontSize: text size.
- fontAlign: Text alignment.
- proportion: Text enlargement ratio, for example, if it is enlarged by 50%, this property is set to 1.5f.
- xProportion: Values > 1.0 stretch the text wider. Values < 1.0 stretch the text narrower.

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(url = "https://www.baidu.com/", backColor = R.color.lightslategray)
    ) {
        append("这是一个链接")
    }
}
```

<figure markdown>
  ![Url text with background](../img/appendable_style_scope_url_bk_color.jpg){ width="400" }
  <figcaption>Url text with background</figcaption>
</figure>

## Special style

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

In addition to common styles, you can also specify the following unique special styles for text, currently supported:

### Url

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(url = "https://www.baidu.com/")) {
        append("这是一个链接")
    }
}
```

<figure markdown>
  ![Url style](../img/appendable_style_string_url.jpg){ width="400" }
</figure>

### Lines indent

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(linesIndent = LeadingMarginSpan.Standard(100, 0))) {
        append("这是一段带首行缩进的文本哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈。")
    }
}
```

![Lines indent style](../img/appendable_style_scope_lines_indent.jpg){ align=left width="400" } 

!!! note "Lines indent setting"

    Click [LeadingMarginSpan.Standard](https://stackoverflow.com/questions/42038931/what-is-leading-margin-in-android) to learn how to use the lines indent.

### Bullet

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(
        AppendableStyle(bulletSpan = BulletSpan(10, ColorUtils.colorHex2Int("#d63031"), 10))
    ) {
        append("这是一段带子弹点的文字。")
    }
}
```

<figure markdown>
  ![Bullet style](../img/appendable_style_scope_bullet.jpg){ width="400" }
</figure>

### Quote

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(
        AppendableStyle(quoteSpan = QuoteSpan(ColorUtils.colorHex2Int("#f0932b"), 10, 10))
    ) {
        append("这是一段引用文字。")
    }
}
```

<figure markdown>
  ![Quote style](../img/appendable_style_scope_quote.jpg){ width="400" }
</figure>

### Strike through or underline

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(
        AppendableStyle(strikeMode = StrikeMode.STRIKETHROUGH)
    ) {
        append("这是一段带删除线的文字。")
    }
    withStyle(
        AppendableStyle(strikeMode = StrikeMode.UNDERLINE)
    ) {
        append("这是一段带下划线的文字。")
    }
}
```

<figure markdown>
  ![Strike through or underline style](../img/appendable_style_scope_strike.jpg){ width="400" }
</figure>

### Script

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle { append("这是一段带上标的文字。") }
    withStyle(AppendableStyle(scriptMode = ScriptMode.SUPERSCRIPT)) {
        append("[1]")
    }
}
```

<figure markdown>
  ![Script style](../img/appendable_style_scope_script.jpg){ width="400" }
</figure>

### Blur

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(
        AppendableStyle(blurRadius = 5f, blur = BlurMaskFilter.Blur.NORMAL)
    ) {
        append("这是一段带模糊的文字。")
    }
}
```

<figure markdown>
  ![Blur style](../img/appendable_style_scope_blur.jpg){ width="400" }
</figure>
