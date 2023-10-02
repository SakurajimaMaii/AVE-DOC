# Screen size

## Get screen width & height

```kotlin
val screenWidth = ScreenSizeUtils.getMobileScreenWidth()
val screenHeight = ScreenSizeUtils.getMobileScreenHeight()
```

!!! note "Screen size with screen orientation"

    Take `2400*1080` as example。

    |         Screen Orientation          | Width | Height |
    | :---------------------------------: | :---: | :----: |
    | Configuration.ORIENTATION_PORTRAIT  | 1080  |  2400  |
    | Configuration.ORIENTATION_LANDSCAPE | 2400  |  1080  |

## Status bar height

```kotlin
val statusBarHeight = ScreenSizeUtils.getStatusBarHeight(this@MainActivity)
```

## Screen Orientation

```kotlin
val screenOrientation = ScreenSizeUtils.getScreenOrientation()
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/informationget/ScreenInfo.kt){ .md-button }
