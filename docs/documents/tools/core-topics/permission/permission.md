# 权限

应用权限有助于保护对以下数据和操作的访问/执行权限，从而为保护用户隐私提供支持：

- 受限数据，例如系统状态和用户的联系信息。
- 受限操作，例如连接到已配对的设备并录制音频。

## 请求结果

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

`requestPermission` 和 `requestMultiplePermissions` 会针对所请求的权限返回三种状态。

- granted/allGranted ：权限已经被授予/全部权限均被授予。
- denied ：权限被拒绝，但是仍可再次请求。
- noMoreAsk ：权限不会再被请求授予。

## 请求单个权限

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

![requestPermission](../img/permission.jpg){ align=right width="200"}

`requestPermission` 允许你进行单个权限的请求，并提供回调以便你对此进行处理。

在 `AndroidManifest.xml` 中声明权限。

```xml
<uses-permission 
    android:name="android.permission.READ_CALENDAR" />
```

调用 `requestPermission` 请求权限。

```kotlin
requestPermission("android.permission.READ_CALENDAR") {
    granted = {

    }
    denied = {

    }
    noMoreAsk = {

    }
}
```

## 请求多个权限

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

![MultiplePermissions](../img/multiple_permissions.gif){ align=right width="200"}

`requestMultiplePermissions` 允许你进行多个权限的请求，并提供回调以便你对此进行处理。

在 `AndroidManifest.xml` 中声明权限。

```xml
<uses-permission 
    android:name="android.permission.READ_CALENDAR" />
<uses-permission 
    android:name="android.permission.READ_SMS" />
```

调用 `requestMultiplePermissions` 请求权限。

```kotlin
requestMultiplePermissions(arrayOf(DATE, SMS)) {
    allGranted = {

    }
    denied = {

    }
    noMoreAsk = {

    }
}
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/PermissionActivity.kt){ .md-button }
