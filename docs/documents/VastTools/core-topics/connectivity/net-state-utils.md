# 网络状态

借助 `NetStateUtils` 你可以很方便的查看一些关于你设备的网络状态。

!!! note "NetworkInfo 和 NetworkCapabilities"

    对于 **API 29** 以下的版本，会获取 [NetworkInfo](https://developer.android.com/reference/android/net/NetworkInfo) 来查看网络是否可用，对于 **API 29** 及以上的版本，会获取 [NetworkCapabilities](https://developer.android.com/reference/android/net/NetworkCapabilities) 来查看网络是否可用。

## 查看网络是否可用

```kotlin
// True为可用，否则为False
val available = isNetworkAvailable()
```

## 查看是否处于WIFI连接

```kotlin
// True为处于WIFI连接，否则为False
val isWifi = isWIFI()
```

## 查看是否处于手机移动网络

```kotlin
// True为处于手机网络连接，否则为False
val isMobile = isMobile()
```

## 查看WIFI信号强度

```kotlin
// signalStrength为信号强度
val signalStrength = getWifiDBM()
```
