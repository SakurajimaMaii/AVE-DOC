# Avatar

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Avatar, used for image or text display.

<figure markdown>
  ![Avatar](../img/avatar.jpg){ width="540" }
</figure>

## Quick start

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

```xml
<com.ave.vastgui.tools.view.avatar.Avatar
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Size

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Size can be set by `avatar_size` or calling `mAvatarSize` .

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
  ![Avatar size](../img/size.jpg){ width="540" }
</figure>

## Shape

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Shape of avatar can be set by `avatar_shape` or calling `setShape` . Currently support:

- Circle
- Round rectangle

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
  ![Avatar shape](../img/shape.jpg){ width="270" }
</figure>

## Color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

The background color of text avatar can be set by  `avatar_background` or calling `mBackground` .

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

## Image

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Image of avatar can be set by `avatar_src` or calling `setAvatar` .

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

## Text

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Text of avatar can be set by `avatar_text` or calling `mText` .

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

## Text color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Color-int of the avatar text can be set by `avatar_text_color` or calling `mTextColor` .

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

## Text size

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Size of avatar text can be set by `avatar_text_size` or calling `mTextSize` .

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

## Stroke color

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Stroke color of avatar can be set by `avatar_stroke_color` or calling `mStrokeColor` .
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

## Stroke width

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

Stroke width of avatar can be set by `avatar_stroke_width` or calling `mStrokeWidth` .

!!! note "Stroke width"

    Depending on the draw order, the actual stroke displayed is 1/2 the value you set. 

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

## Round corner radius

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

When the shape of avatar is round rctangle, round corner radius can be set by `avatar_corner_radius` or calling `mCornerRadius` .

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

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AvatarActivity.kt){ .md-button }
