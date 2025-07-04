# 网络状态

`NetStateUtils` 提供了一系列获取网络状态的方法。主要分为 `isXXX` 和 `hasXXX` ，其中 `isXXX` 用来判断**当前活动的默认网络**状态， `hasXXX` 用来判断所有存在的网络连接状态。

!!! note "NetworkInfo 和 NetworkCapabilities"

    对于 **API 29** 以下的版本，会获取 [NetworkInfo](https://developer.android.com/reference/android/net/NetworkInfo) 来查看网络是否可用，对于 **API 29** 及以上的版本，会获取 [NetworkCapabilities](https://developer.android.com/reference/android/net/NetworkCapabilities) 来查看网络是否可用。

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/androidTest/kotlin/NetStateUtilsTest.kt){ .md-button }
