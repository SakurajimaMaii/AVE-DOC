# App shortcut

## Create pinned shortcuts

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

![AppShortcuts](../img/app_shortcuts.png){ align=right width="300" }

On Android 8.0 (API level 26) and higher, you can create pinned shortcuts. Unlike static and dynamic shortcuts, pinned shortcuts appear in supported launchers as separate icons. Figure 1 shows the distinction between these two types of shortcuts.

!!! note  
    
    Note: When you attempt to pin a shortcut onto a supported launcher, the user receives a confirmation dialog asking their permission to pin the shortcut. If the user doesn't allow the shortcut to be pinned, the launcher cancels the request.

The following example shows you how to create an application shortcut.

```kotlin
createPinnedShortcut("OnlyId") {
    return@createPinnedShortcut Intent(context, MainActivity::class.java)
}
```

### Set resultIntent for shortcut

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

Set resultIntent by `shortcutResultIntent` .

```kotlin
createPinnedShortcut(
    shortcutId = "OnlyId",
    shortcutResultIntent = { intent ->
        PendingIntent.getBroadcast(context, 0, intent, PendingIntent.FLAG_IMMUTABLE)
    }
) {
    return@createPinnedShortcut Intent(context, MainActivity::class.java).apply {
        action = Intent.ACTION_VIEW
    }
}
```

## Create dynamic shortcuts

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

![DynamicShortcuts](../img/dynamic_shortcuts.png){ align=right width="300" }

Using `DynamicShortcuts` to create dynamic shortcuts.

```kotlin
val shortcut = ShortcutInfoCompat.Builder(context, "OnlyId")
    .setShortLabel("Website")
    .setLongLabel("Open the website")
    .setIcon(IconCompat.createWithResource(
        context, R.drawable.ic_launcher_foreground))
    .setIntent(Intent(Intent.ACTION_VIEW,
        Uri.parse("https://www.mysite.example.com/")))
    .build()
addDynamicShortcuts(listOf(shortcut))
```

## Sample code

[Sample Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/AppShortcuts.kt){ .md-button }
