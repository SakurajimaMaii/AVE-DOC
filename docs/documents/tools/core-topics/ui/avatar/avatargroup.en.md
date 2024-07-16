# AvatarGroup

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

You can use `AvatarGroup` component to display avatars as a group.

## Quick start

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

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

[Default style](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/VastTools/src/main/res/values/styles.xml){ .md-button }

## Overlap from

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

The coverage direction of the avatars with overlapFrom can be set by `avatar_overlap_from` or calling `setOverlapFrom` .

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
</center>

## Overlap width

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

The width can be set by `avatar_overlap_distance` or calling `setOverlapDistance` .

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
</center>

## Add Avatar

[:octicons-tag-24: Version 0.5.4](https://ave.entropy2020.cn/version/VastTools/#054)

1. Create `Avatar`

    ```kotlin
    val mAvatar = Avatar(this).apply {
        setAvatar(R.drawable.img_avatar_1)
    }
    ```

2. Add avatar by `addView`

    ```kotlin
    mBinding.avatarGroupStart.addView(
        mAvatar, LayoutParams(LayoutParams.WRAP_CONTENT, LayoutParams.WRAP_CONTENT)
    )
    ```

<figure markdown>
  ![AvatarGroup Add Avatar](../img/avatar_group_add_avatar.jpg){ width="270" }
</figure>

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/AvatarActivity.kt){ .md-button }
