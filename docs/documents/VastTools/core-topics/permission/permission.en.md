# Permission

App permissions help support user privacy by protecting access to the following:

- Restricted data, such as system state and users' contact information.
- Restricted actions, such as connecting to a paired device and recording audio.

## Permission request result 

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

`requestPermission` and `requestMultiplePermissions` return three statuses for the requested permissions.

- granted/allGranted: permission has been granted/all permissions have been granted.
- denied : The permission was denied, but can still be requested again.
- noMoreAsk : The permission will not be asked to be granted again.

## Request single permission

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

![requestPermission](../img/permission.jpg){ align=right width="200"}

`requestPermission` allows you to make a request for a single permission, and provides a callback for you to handle it.

Declare permission in `AndroidManifest.xml` .

```xml
<uses-permission 
    android:name="android.permission.READ_CALENDAR" />
```

Call `requestPermission` .

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

## Request multiple permissions

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/VastTools/#020)

![MultiplePermissions](../img/multiple_permissions.gif){ align=right width="200"}

`requestMultiplePermissions` allows you to request multiple permissions and provides callbacks for you to handle it.

Declare permissions in `AndroidManifest.xml` .

```xml
<uses-permission 
    android:name="android.permission.READ_CALENDAR" />
<uses-permission 
    android:name="android.permission.READ_SMS" />
```

Call `requestMultiplePermissions` .

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

## Example Code

[Example Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/PermissionActivity.kt){ .md-button }
