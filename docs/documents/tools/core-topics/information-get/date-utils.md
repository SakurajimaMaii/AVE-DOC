# 日期工具

## 默认的时间格式

```kotlin
const val FORMAT_YYYY_MM_DD = "yyyy-MM-dd"
const val FORMAT_YYYY_MM_DD_HH_MM_SS = "yyyy-MM-dd HH:mm:ss"
const val FORMAT_YYYY_MM = "yyyy-MM"
const val FORMAT_YYYY = "yyyy"
const val FORMAT_HH_MM = "HH:mm"
const val FORMAT_HH_MM_SS = "HH:mm:ss"
const val FORMAT_MM_SS = "mm:ss"
const val FORMAT_MM_DD_HH_MM = "MM-dd HH:mm"
const val FORMAT_MM_DD_HH_MM_SS = "MM-dd HH:mm:ss"
const val FORMAT_YYYY_MM_DD_HH_MM = "yyyy-MM-dd HH:mm"
const val FORMAT_YYYY2MM2DD = "yyyy.MM.dd"
const val FORMAT_YYYY2MM2DD_HH_MM = "yyyy.MM.dd HH:mm"
const val FORMAT_MMCDDC_HH_MM = "MM月dd日 HH:mm"
const val FORMAT_MMCDDC = "MM月dd日"
const val FORMAT_YYYYCMMCDDC = "yyyy年MM月dd日"
```

## 支持的时区

```kotlin
const val GMT_PLUS_ZONE = "GMT+00:00"
const val GMT_PLUS_ONE = "GMT+01:00"
const val GMT_PLUS_TWO = "GMT+02:00"
const val GMT_PLUS_THREE = "GMT+03:00"
const val GMT_PLUS_FOUR = "GMT+04:00"
const val GMT_PLUS_FIVE = "GMT+05:00"
const val GMT_PLUS_SIX = "GMT+06:00"
const val GMT_PLUS_SEVEN = "GMT+07:00"
const val GMT_PLUS_EIGHT = "GMT+08:00"
const val GMT_PLUS_NINE = "GMT+09:00"
const val GMT_PLUS_TEN = "GMT+10:00"
const val GMT_PLUS_ELEVEN = "GMT+11:00"
const val GMT_PLUS_TWELVE = "GMT+12:00"
const val GMT_MINUS_ONE = "GMT-01:00"
const val GMT_MINUS_TWO = "GMT-02:00"
const val GMT_MINUS_THREE = "GMT-03:00"
const val GMT_MINUS_FOUR = "GMT-04:00"
const val GMT_MINUS_FIVE = "GMT-05:00"
const val GMT_MINUS_SIX = "GMT-06:00"
const val GMT_MINUS_SEVEN = "GMT-07:00"
const val GMT_MINUS_EIGHT = "GMT-08:00"
const val GMT_MINUS_NINE = "GMT-09:00"
const val GMT_MINUS_TEN = "GMT-10:00"
const val GMT_MINUS_ELEVEN = "GMT-11:00"
const val GMT_MINUS_TWELVE = "GMT-12:00"
```

## 按照指定格式获取当前时间

`getCurrentTime` 会按照指定格式输出当前的时间。

```kotlin
// 返回 14:18 作为dateString的值
DateUtils.getCurrentTime(DateUtils.FORMAT_HH_MM))
```

## 获取当前时间之前或之后的天数的时间

`getDayBeforeOrAfterCurrentTime` 会获取当前时间之前或之后的天数，并按照指定格式的时间。

```kotlin
// 返回 05-28 14:18:08
DateUtils.getDayBeforeOrAfterCurrentTime(DateUtils.FORMAT_MM_DD_HH_MM_SS,-2)
```

## 获取设备当前所在时区

```kotlin
// 返回 GMT+00:00
DateUtils.currentTimeZone
```

## 根据给定的时间字符串和格式获取 Date 对象

```kotlin
val date: Date = DateUtils.datetimeFromString("14:18", FORMAT_HH_MM)
```

## 将给定的 Date 解析为时间字符串

```kotlin
// 获取一个Date对象
val date: Date = DateUtils.datetimeFromString("14:18", DateUtils.FORMAT_HH_MM)
// 返回 14:18:00
DateUtils.datetimeToString(date, DateUtils.FORMAT_HH_MM_SS)
```

## 根据给定的时区和时间格式返回对应的字符串

`dateTimeToGMT` 默认情况下，按照 `yyyy-MM-dd HH:mm:ss` 和当前所处的时区获取字符串。

```kotlin
// 返回 2023-05-30 14:18:08
DateUtils.dateTimeToGMT()
// 返回 2023.05.30 20:18
DateUtils.dateTimeToGMT(DateUtils.GMT_PLUS_SIX,DateUtils.FORMAT_YYYY2MM2DD_HH_MM)
```

## 根据给定的 UTC 时间和格式解析出当前时间

`dateTimeFromGMT` 会根据给定的时间返回当前设备所在时区的时间，并按照对应的格式返回。

```kotlin
// 返回 15:01
DateUtils.dateTimeFromGMT("07:01",DateUtils.FORMAT_HH_MM)
```

## 获取本周开始(或结束)时间，周一是第一天

`weekStartTime` 和 `weekEndTime` 的默认时间格式是 `FORMAT_YYYY_MM_DD_HH_MM_SS` 。

```kotlin
// 返回 2023-05-29 14:18:08
DateUtils.weekStartTime()
// 返回 2023-06-04 14:18:08
DateUtils.weekEndTime()
```

## 获取本周开始(或结束)的时间，周日是第一天

`getWeekStartTime` 和 `getWeekEndTime` 的默认时间格式是 `FORMAT_YYYY_MM_DD_HH_MM_SS` 。

```kotlin
// 返回 2023-05-28 14:18:08
DateUtils.getWeekStartTime()
// 返回 2023-06-03 14:18:08
DateUtils.getWeekEndTime()
```
