# NetState

With `NetStateUtils` you can easily check some network status about your device

!!! note "NetworkInfo and NetworkCapabilities"

    For versions below **API 29**, [NetworkInfo](https://developer.android.com/reference/android/net/NetworkInfo) will be obtained to check whether the network is available. For **API 29** and above version, [NetworkCapabilities](https://developer.android.com/reference/android/net/NetworkCapabilities) will be obtained to check whether the network is available.

## Check if the network is available

```kotlin
// True is available, otherwise False
val available = isNetworkAvailable()
```

## Check if it is connected to WIFI

```kotlin
// True is in WIFI connection, otherwise False
val isWifi = isWIFI()
```

## Check if you are on the mobile network

```kotlin
// True is in the mobile network connection, otherwise False
val isMobile = isMobile()
```

## Check WIFI signal strength

```kotlin
// signalStrength is the signal strength
val signalStrength = getWifiDBM()
```
