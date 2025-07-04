# Avatar

[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

Avatar, used for image or text display.

<figure markdown>
  ![Avatar](../img/avatar.jpg){ width="540" }
</figure>

## Quick start

[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

```xml
<com.ave.vastgui.tools.view.avatar.Avatar
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/main/res/values/styles.xml){ .md-button }

## Size

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Size can be set by `avatar_size` or calling `size` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.size = 60f.DP
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

The background color of text avatar can be set by  `avatar_background` or calling `srcColor` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.srcColor = getColor(R.color.aquamarine)
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054)

Image of avatar can be set by `avatar_src` or calling `setAvatar` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.setAvatar(R.drawable.img_avatar)
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Text of avatar can be set by `avatar_text` or calling `srcText` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.srcText = "B"
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Color-int of the avatar text can be set by `avatar_text_color` or calling `srcTextColor` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.srcTextColor = getColor(R.color.burlywood)
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Size of avatar text can be set by `avatar_text_size` or calling `srcTextSize` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.srcTextSize = 16f.SP
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Stroke color of avatar can be set by `avatar_stroke_color` or calling `strokeColor` .
=== "Kotlin"

    ```kotlin
    binding.imgAvatar.strokeColor = getColor(R.color.blue)
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

Stroke width of avatar can be set by `avatar_stroke_width` or calling `strokeWidth` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.strokeWidth = 6f.DP
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

> Add:[:octicons-tag-24: Version 0.5.4](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#054) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

When the shape of avatar is round rctangle, round corner radius can be set by `avatar_corner_radius` or calling `cornerRadius` .

=== "Kotlin"

    ```kotlin
    binding.imgAvatar.cornerRadius = 6f.DP
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
