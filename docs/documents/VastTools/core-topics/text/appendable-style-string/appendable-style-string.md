# 多种样式文字

`appendableStyleScope` 允许你快速构建多种样式文字。

<figure markdown>
  ![AppendableStyleScope](../img/appendable_style_scope.jpg){ width="400" }
  <figcaption>AppendableStyleScope</figcaption>
</figure>

## 特性

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

- 支持对于同一个字符串设置多种样式。
- 支持文字和图片。
- 提供默认样式。
- 采用 DSL 确保更清晰的样式作用范围

## 快速开始

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

下面的示例为你展示了如何创建一条链接文本。

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(url = "https://www.baidu.com/")) {
        append("这是一个链接")
    }
}
```
下面的示例为你展示了如何创建一条图片文本。

```kotlin
appendableStyleScope(getBinding().tv) {
    withImage(ImageSpan(this, R.mipmap.ic_launcher))
}
```

## 拼接字符串

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

下面的示例为你展示如何创建一条复杂的富文本字符串。

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

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/text/AppendableStyleActivity.kt){ .md-button }

## 通用样式

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

通过指定 `AppendableStyle` 内的 `backColor` 属性，可以为字符串设置背景色。目前 `AppendableStyle` 允许你指定以下属性：

- foreColor ： 文字颜色。
- backColor ： 文字背景色。
- fontStyle ： 文字风格，目前支持粗体、斜体或者正常。
- fontFamily ： 文字字体。
- fontSize ： 文字大小。
- fontAlign ： 文字对齐方式。
- proportion ： 文字放大比例，例如如果放大 50% ，则该属性设置为 1.5f 。
- xProportion ： 值 > 1.0 会将文本拉伸得更宽。值 < 1.0 会将文本拉伸得更窄。

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(url = "https://www.baidu.com/", backColor = R.color.lightslategray)
    ) {
        append("这是一个链接")
    }
}
```

<figure markdown>
  ![AppendableStyleString](../img/appendable_style_scope_url_bk_color.jpg){ width="400" }
  <figcaption>带背景色的链接</figcaption>
</figure>

## 特殊样式

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

除了通用样式，你也可以为文字指定以下唯一的特殊样式，目前支持：

### 链接文字

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(url = "https://www.baidu.com/")) {
        append("这是一个链接")
    }
}
```

<figure markdown>
  ![AppendableStyleString-Url](../img/appendable_style_string_url.jpg){ width="400" }
</figure>

### 首行缩进

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle(AppendableStyle(linesIndent = LeadingMarginSpan.Standard(100, 0))) {
        append("这是一段带首行缩进的文本哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈。")
    }
}
```

![AppendableStyleString-linesIndent](../img/appendable_style_scope_lines_indent.jpg){ align=left width="400" } 

!!! note "linesIndent 参数的设置"

    关于 `linesIndent` 参数，你可以参考 [LeadingMarginSpan.Standard](https://stackoverflow.com/questions/42038931/what-is-leading-margin-in-android)

### 携带子弹点

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
  ![AppendableStyleString-Bullet](../img/appendable_style_scope_bullet.jpg){ width="400" }
</figure>

### 引用文字

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
  ![AppendableStyleString-Quote](../img/appendable_style_scope_quote.jpg){ width="400" }
</figure>

### 删除线或者下划线

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
  ![AppendableStyleString-Strike](../img/appendable_style_scope_strike.jpg){ width="400" }
</figure>

### 上标或者下标

```kotlin
appendableStyleScope(getBinding().tv) {
    withStyle { append("这是一段带上标的文字。") }
    withStyle(AppendableStyle(scriptMode = ScriptMode.SUPERSCRIPT)) {
        append("[1]")
    }
}
```

<figure markdown>
  ![AppendableStyleString-Script](../img/appendable_style_scope_script.jpg){ width="400" }
</figure>

### 范围模糊

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
  ![AppendableStyleString-Blur](../img/appendable_style_scope_blur.jpg){ width="400" }
</figure>

### 可点击文字

该项不提供示例。
