# 应用快捷方式

## 创建固定快捷方式

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

![AppShortcuts](../img/app_shortcuts.png){ align=right width="300" }

在 Android 8.0（API 级别 26）及更高版本中，您可以创建固定快捷方式。与静态和动态快捷方式不同，固定快捷方式在受支持的启动器中显示为单独的图标。右图显示了这两类快捷方式之间的区别。

!!! note  
    
    注意：当您尝试将快捷方式固定到受支持的启动器上时，用户会收到一个确认对话框，询问其是否允许固定该快捷方式。如果用户不允许固定该快捷方式，启动器会取消这一请求。

下面的示例向你展示了如何创建一个应用快捷方式

```kotlin
createPinnedShortcut("OnlyId") {
    return@createPinnedShortcut Intent(context, MainActivity::class.java)
}
```

### 为快捷方式设置 resultIntent

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

通过 `shortcutResultIntent` 参数设置 resultIntent 。

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

## 创建动态快捷方式

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

![DynamicShortcuts](../img/dynamic_shortcuts.png){ align=right width="300" }

调用 `DynamicShortcuts` 来创建一个动态快捷方式。

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

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/AppShortcuts.kt){ .md-button }
