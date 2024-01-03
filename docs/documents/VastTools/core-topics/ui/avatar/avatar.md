# 头像

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

头像控件支持图片和文字展示。

<figure markdown>
  ![Avatar](../img/avatar.jpg){ width="540" }
</figure>

## 快速开始

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

```xml
<com.ave.vastgui.tools.view.avatar.Avatar
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 设置大小

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_size` 或者调用 `mAvatarSize` 来设置头像的大小。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mAvatarSize = 60f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_size="60dp" />
    ```

<figure markdown>
  ![Avatar Size](../img/size.jpg){ width="540" }
</figure>

## 设置形状

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_shape` 或者调用 `setShape` 来设置头像的形状。目前支持以下形状：

- 圆形
- 圆角矩形

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.setShape(Avatar.SHAPE_CIRCLE)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_shape="round" />
    ```

<figure markdown>
  ![Avatar Shape](../img/shape.jpg){ width="270" }
</figure>

## 设置颜色

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_background` 或者调用 `mBackground` 来设置文字头像的背景色。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mBackground = getColor(R.color.aquamarine)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_background="#e84118" />
    ```

<figure markdown>
  ![Avatar Color](../img/color.jpg){ width="540" }
</figure>

## 设置图片

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_src` 或者调用 `setAvatar` 来设置头像的图片。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.setAvatar(R.drawable.img_avatar)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_src="@drawable/img_avatar" />
    ```

<figure markdown>
  ![Avatar Image](../img/image.jpg){ width="100" }
</figure>

## 设置文字

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_text` 或者调用 `mText` 来设置头像的显示文字。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mText = "B"
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_text="B" />
    ```

<figure markdown>
  ![Avatar Text](../img/text.jpg){ width="540" }
</figure>

## 设置文字颜色

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_text_color` 或者调用 `mTextColor` 来设置文字颜色。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mTextColor = getColor(R.color.burlywood)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_text_color="#c8d6e5" />
    ```

<figure markdown>
  ![Avatar Text Color](../img/text_color.jpg){ width="540" }
</figure>

## 设置文字大小

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_text_size` 或者调用 `mTextSize` 来设置头像的显示文字大小。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mTextSize = 16f.SP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_text_size="16sp" />
    ```

<figure markdown>
  ![Avatar Text Size](../img/text_size.jpg){ width="540" }
</figure>

## 设置描边

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_stroke_color` 或者调用 `mStrokeColor` 来设置头像的描边颜色。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mStrokeColor = getColor(R.color.blue)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_stroke_color="#f0932b" />
    ```

<figure markdown>
  ![Avatar Stroke Color](../img/stroke_color.jpg){ width="540" }
</figure>

## 设置描边宽度

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_stroke_width` 或者调用 `mStrokeWidth` 来设置头像的描边宽度。

!!! note "描边宽度说明"

    根据绘制顺序，实际显示的描边为你设置值的 1/2 。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mStrokeWidth = 6f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_stroke_width="6dp" />
    ```

<figure markdown>
  ![Avatar Stroke Width](../img/stroke_width.jpg){ width="540" }
</figure>

## 矩形圆角

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

可以通过 `avatar_corner_radius` 或者 `mCornerRadius` 来设置矩形圆角半径。

!!! note "矩形圆角说明"

    只有当头像为圆角模式才会生效 。

=== "Kotlin"

    ```kotlin
    mBinding.imgAvatar.mCornerRadius = 6f.DP
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.Avatar
        ... 
        app:avatar_corner_radius="6dp" />
    ```

<figure markdown>
  ![Avatar Corner Radius](../img/corner_radius.jpg){ width="540" }
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AvatarActivity.kt){ .md-button }
