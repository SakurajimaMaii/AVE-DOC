# 头像组

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

可以通过 `AvatarGroup` 将 `Avatar` 显示为组。

## 快速开始

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

```xml
<com.ave.vastgui.tools.view.avatar.AvatarGroup
    android:layout_width="wrap_content"
    android:layout_height="wrap_content">

    <com.ave.vastgui.tools.view.avatar.Avatar
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <com.ave.vastgui.tools.view.avatar.Avatar
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <com.ave.vastgui.tools.view.avatar.Avatar
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
</com.ave.vastgui.tools.view.avatar.AvatarGroup>
```

[查看默认样式](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## 覆盖方式

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

可以通过 `avatar_overlap_from` 或者调用 `setOverlapFrom` 来设置头像的覆盖方式。

=== "Kotlin"

    ```kotlin
    mBinding.avatarGroupStart.setOverlapFrom(AvatarGroup.END)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.AvatarGroup
        ...
        app:avatar_overlap_from="end">

        ... // Avatar

    </com.ave.vastgui.tools.view.avatar.AvatarGroup>
    ```

<center>
![Avatar Group Start](../img/avatar_group_start.jpg){ width="270" }
![Avatar Group End](../img/avatar_group_end.jpg){ width="270" }
<figcaption>左边Start 右边End</figcaption>
</center>

## 覆盖宽度

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

可以通过 `avatar_overlap_distance` 或者调用 `setOverlapDistance` 来设置头像的覆盖长度。

=== "Kotlin"

    ```kotlin
    mBinding.avatarGroupStart.setOverlapDistance(20f.DP)
    ```

=== "Xml"

    ```xml
    <com.ave.vastgui.tools.view.avatar.AvatarGroup
        ...
        app:avatar_overlap_distance="20dp">

        ... // Avatar

    </com.ave.vastgui.tools.view.avatar.AvatarGroup>
    ```

<center>
![Avatar Distance Original](../img/avatar_group_distance_original.jpg){ width="270" }
![Avatar Distance 20dp](../img/avatar_group_distance_20dp.jpg){ width="270" }
<figcaption>左边为默认长度 右边为20dp</figcaption>
</center>

## 动态添加头像

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/tools/#054)

1. 创建 `Avatar` 对象

    ```kotlin
    val mAvatar = Avatar(this).apply {
        setAvatar(R.drawable.img_avatar_1)
    }
    ```

2. 使用 `addView` 添加头像

    ```kotlin
    mBinding.avatarGroupStart.addView(
        mAvatar, LayoutParams(LayoutParams.WRAP_CONTENT, LayoutParams.WRAP_CONTENT)
    )
    ```

<figure markdown>
  ![AvatarGroup Add Avatar](../img/avatar_group_add_avatar.jpg){ width="270" }
  <figcaption>动态添加头像</figcaption>
</figure>

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AvatarActivity.kt){ .md-button }
