# 屏幕信息

## 获取屏幕长宽的方法

```kotlin
val screenWidth = ScreenSizeUtils.getMobileScreenWidth()
val screenHeight = ScreenSizeUtils.getMobileScreenHeight()
```

!!! note "返回的屏幕尺寸与当前屏幕的朝向有关"

    屏幕尺寸以 2400*1080为例。

    |              屏幕朝向               | 返回宽度 | 返回高度 |
    | :---------------------------------: | :------: | :------: |
    | Configuration.ORIENTATION_PORTRAIT  |   1080   |   2400   |
    | Configuration.ORIENTATION_LANDSCAPE |   2400   |   1080   |

## 获取状态栏高度

```kotlin
val statusBarHeight = ScreenSizeUtils.getStatusBarHeight(this@MainActivity)
```

## 获取屏幕方向

```kotlin
val screenOrientation = ScreenSizeUtils.getScreenOrientation()
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/informationget/ScreenInfo.kt){ .md-button }
