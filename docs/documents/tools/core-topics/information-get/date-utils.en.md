# Date 

## Default time format

| Name                       | Value                |
| -------------------------- | -------------------- |
| FORMAT_YYYYhMMhDD          | yyyy-MM-dd           |
| FORMAT_YYYY_MM_DD_HH_MM_SS | yyyy-MM-dd HH\:mm:ss |
| FORMAT_YYYY_MM             | yyyy-MM              |
| FORMAT_YYYY                | yyyy                 |
| FORMAT_HH_MM               | HH:mm                |
| FORMAT_HH_MM_SS            | HH\:mm:ss            |
| FORMAT_MM_SS               | mm:ss                |
| FORMAT_MM_DD_HH_MM         | MM-dd HH:mm          |
| FORMAT_MM_DD_HH_MM_SS      | MM-dd HH\:mm:ss      |
| FORMAT_YYYY_MM_DD_HH_MM    | yyyy-MM-dd HH:mm     |
| FORMAT_YYYY2MM2DD          | yyyy.MM.dd           |
| FORMAT_YYYY2MM2DD_HH_MM    | yyyy.MM.dd HH:mm     |
| FORMAT_MMCDDC_HH_MM        | MM月dd日 HH:mm       |
| FORMAT_MMCDDC              | MM月dd日             |
| FORMAT_YYYYCMMCDDC         | yyyy年MM月dd日       |

## Support timezone

| Name             | Value     |
| ---------------- | --------- |
| GMT_PLUS_ZONE    | GMT+00:00 |
| GMT_PLUS_ONE     | GMT+01:00 |
| GMT_PLUS_TWO     | GMT+02:00 |
| GMT_PLUS_THREE   | GMT+03:00 |
| GMT_PLUS_FOUR    | GMT+04:00 |
| GMT_PLUS_FIVE    | GMT+05:00 |
| GMT_PLUS_SIX     | GMT+06:00 |
| GMT_PLUS_SEVEN   | GMT+07:00 |
| GMT_PLUS_EIGHT   | GMT+08:00 |
| GMT_PLUS_NINE    | GMT+09:00 |
| GMT_PLUS_TEN     | GMT+10:00 |
| GMT_PLUS_ELEVEN  | GMT+11:00 |
| GMT_PLUS_TWELVE  | GMT+12:00 |
| GMT_MINUS_ONE    | GMT-01:00 |
| GMT_MINUS_TWO    | GMT-02:00 |
| GMT_MINUS_THREE  | GMT-03:00 |
| GMT_MINUS_FOUR   | GMT-04:00 |
| GMT_MINUS_FIVE   | GMT-05:00 |
| GMT_MINUS_SIX    | GMT-06:00 |
| GMT_MINUS_SEVEN  | GMT-07:00 |
| GMT_MINUS_EIGHT  | GMT-08:00 |
| GMT_MINUS_NINE   | GMT-09:00 |
| GMT_MINUS_TEN    | GMT-10:00 |
| GMT_MINUS_ELEVEN | GMT-11:00 |
| GMT_MINUS_TWELVE | GMT-12:00 |

## Get date with given format

`getCurrentTime` will output the current time in the given format.

```kotlin
// Return 14:18 
DateUtils.getCurrentTime(DateUtils.FORMAT_HH_MM))
```

## Get date before or after current time

`getDayBeforeOrAfterCurrentTime` will get the number of days before or after the current time, and the time according to the given format.

```kotlin
// Return 05-28 14:18:08
DateUtils.getDayBeforeOrAfterCurrentTime(DateUtils.FORMAT_MM_DD_HH_MM_SS,-2)
```

## Get current timezone

> Add:[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

```kotlin
// Return GMT+00:00
val timezome = DateUtils.getCurrentTimeZone(DateUtils.SHORT)
```

## Get date object by time string and time format

```kotlin
val date: Date = DateUtils.datetimeFromString("14:18", FORMAT_HH_MM)
```

## Get time string by parsing date object

```kotlin
val date: Date = DateUtils.datetimeFromString("14:18", DateUtils.FORMAT_HH_MM)
DateUtils.datetimeToString(date, DateUtils.FORMAT_HH_MM_SS)
```

## Get time string by parsing timezone and time format.

```kotlin
// Return 2023-05-30 14:18:08
DateUtils.dateTimeToGMT()
// Return 2023.05.30 20:18
DateUtils.dateTimeToGMT(DateUtils.GMT_PLUS_SIX,DateUtils.FORMAT_YYYY2MM2DD_HH_MM)
```

## Parse the current time according to the given UTC time and format

```kotlin
// Return 15:01
DateUtils.dateTimeFromGMT("07:01",DateUtils.FORMAT_HH_MM)
```

## Get the start (or end) time of this week, Monday is the first day

The default time format for `weekStartTime` and `weekEndTime` is `FORMAT_YYYY_MM_DD_HH_MM_SS` .

```kotlin
// Return 2023-05-29 14:18:08
DateUtils.weekStartTime()
// Return 2023-06-04 14:18:08
DateUtils.weekEndTime()
```

## Get the start (or end) time of the week, with Sunday being the first day

The default time format for `getWeekStartTime` and `getWeekEndTime` is `FORMAT_YYYY_MM_DD_HH_MM_SS` .

```kotlin
// Return 2023-05-28 14:18:08
DateUtils.getWeekStartTime()
// Return 2023-06-03 14:18:08
DateUtils.getWeekEndTime()
```
