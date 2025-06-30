# Network State

`NetStateUtils` provides a series of methods to get the network state. They are divided into `isXXX` and `hasXXX`, where `isXXX` is used to determine the status of the **current active default data network** and `hasXXX` is used to determine the status of all existing network connections.

!!! note "NetworkInfo and NetworkCapabilities"

    For versions below **API 29**, [NetworkInfo](https://developer.android.com/reference/android/net/NetworkInfo) will be obtained to check whether the network is available. For **API 29** and above version, [NetworkCapabilities](https://developer.android.com/reference/android/net/NetworkCapabilities) will be obtained to check whether the network is available.

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/libraries/tools/src/androidTest/kotlin/NetStateUtilsTest.kt){ .md-button }
