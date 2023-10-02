# App information

You can get app information by `AppUtils` .

![AppUtils](../img/app_utils.png){ align=right width="250" }

```kotlin
@Composable
fun AppInfo() {
    val appInfo = mapOf(
        "getPackageName" to AppUtils.getPackageName(),
        "getAppName" to AppUtils.getAppName(),
        "getVersionName" to AppUtils.getVersionName(),
        "getVersionCode" to AppUtils.getVersionCode().toString(),
        "getAppDebug" to AppUtils.getAppDebug().toString()
    ).toList()

    Column {
        Text(
            text = "Function name: getAppBitmap",
            modifier = Modifier.padding(15.dp)
        )

        Image(
            bitmap = AppUtils.getAppBitmap().asImageBitmap(),
            contentDescription = null,
            modifier = Modifier.padding(15.dp)
        )

        LazyColumn(modifier = Modifier.fillMaxSize()) {
            items(appInfo) { item ->
                ListItem(
                    headlineText = {
                        Text(text = "Function name: ${item.first}")
                    },
                    supportingText = {
                        Text(text = item.second)
                    }
                )
            }
        }
    }
}
```

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/informationget/AppInfo.kt){ .md-button }
