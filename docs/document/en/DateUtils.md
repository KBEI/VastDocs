# DateUtils

## Supported time formats

```java
public static final String DATE_FORMAT = "yyyy-MM-dd";
public static final String TIME_FORMAT = "yyyy-MM-dd HH:mm:ss";
public static final String FORMAT_YYYY_MM = "yyyy-MM";
public static final String FORMAT_YYYY = "yyyy";
public static final String FORMAT_HH_MM = "HH:mm";
public static final String FORMAT_HH_MM_SS = "HH:mm:ss";
public static final String FORMAT_MM_SS = "mm:ss";
public static final String FORMAT_MM_DD_HH_MM = "MM-dd HH:mm";
public static final String FORMAT_MM_DD_HH_MM_SS = "MM-dd HH:mm:ss";
public static final String FORMAT_YYYY_MM_DD_HH_MM = "yyyy-MM-dd HH:mm";
public static final String FORMAT_YYYY2MM2DD = "yyyy.MM.dd";
public static final String FORMAT_YYYY2MM2DD_HH_MM = "yyyy.MM.dd HH:mm";
public static final String FORMAT_MMCDD_HH_MM = "MM月dd日 HH:mm";
public static final String FORMAT_MMCDD = "MM月dd日";
public static final String FORMAT_YYYYCMMCDD = "yyyy年MM月dd日";
```

## Supported time zones

```java
public static final String GMT_PLUS_ZONE = "GMT+00:00";
public static final String GMT_PLUS_ONE = "GMT+01:00";
public static final String GMT_PLUS_TWO = "GMT+02:00";
public static final String GMT_PLUS_THREE = "GMT+03:00";
public static final String GMT_PLUS_FOUR = "GMT+04:00";
public static final String GMT_PLUS_FIVE = "GMT+05:00";
public static final String GMT_PLUS_SIX = "GMT+06:00";
public static final String GMT_PLUS_SEVEN = "GMT+07:00";
public static final String GMT_PLUS_EIGHT = "GMT+08:00";
public static final String GMT_PLUS_NINE = "GMT+09:00";
public static final String GMT_PLUS_TEN = "GMT+10:00";
public static final String GMT_PLUS_ELEVEN = "GMT+11:00";
public static final String GMT_PLUS_TWELVE = "GMT+12:00";
public static final String GMT_MINUS_ONE = "GMT-01:00";
public static final String GMT_MINUS_TWO = "GMT-02:00";
public static final String GMT_MINUS_THREE = "GMT-03:00";
public static final String GMT_MINUS_FOUR = "GMT-04:00";
public static final String GMT_MINUS_FIVE = "GMT-05:00";
public static final String GMT_MINUS_SIX = "GMT-06:00";
public static final String GMT_MINUS_SEVEN = "GMT-07:00";
public static final String GMT_MINUS_EIGHT = "GMT-08:00";
public static final String GMT_MINUS_NINE = "GMT-09:00";
public static final String GMT_MINUS_TEN = "GMT-10:00";
public static final String GMT_MINUS_ELEVEN = "GMT-11:00";
public static final String GMT_MINUS_TWELVE = "GMT-12:00";
```

## Get current time

for example:

```kotlin
Log.i("VU",DateUtils.currentTime)
```

result:

```
// By default, the result is based on month, year, day, hour, minute and second
2022-02-08 12:34:15.921 11132-11132/com.gcode.vastutils I/VU: 2022-02-08 12:34:15
```

## Get the current time zone of the device

for example:

```kotlin
Log.i("VU",DateUtils.currentTimeZone)
```

result:

```
2022-02-08 12:39:07.938 13174-13174/com.gcode.vastutils I/VU: GMT+08:00
```

## Gets the Date object of the current minimum date

for example:

```kotlin
val date: Date = DateUtils.minDate()
```

## The minimum date string parsed in the specified format

for example:

```kotlin
// If no parameter is added, it will be parsed in the format of yyyy-MM-dd HH:mm:ss by default.
Log.i("VU",DateUtils.minDateToString())
// If add format parameters of FORMAT_HH_MM,it will return only hours and minutes.
Log.i("VU",DateUtils.minDateToString(FORMAT_HH_MM))
```

result:

```kotlin
// Default format.
2022-02-08 14:20:30.002 17203-17203/com.gcode.vastutils I/VU: 1900-02-01 14:20:30
// Results in the given format.
2022-02-08 14:18:51.090 16270-16270/com.gcode.vastutils I/VU: 14:18
```

## Gets the Date object according to the given time string and format

for example:

```kotlin
val date: Date? = DateUtils.datetimeFromString("14:18", FORMAT_HH_MM)
```

## Resolves the given Date to a time string

for example:

```kotlin
// Get a Date object
val date: Date? = DateUtils.datetimeFromString("14:18", FORMAT_HH_MM)
// Print time string in log
Log.i("VU",DateUtils.datetimeToString(date!!, FORMAT_HH_MM_SS))
```

result:

```kotlin
2022-02-08 14:40:07.019 2431-2431/com.gcode.vastutils I/VU: 14:18:00
```

## Get current local time string by parsing the utcTime in dateFormat format

for example:

```kotlin
// By default, the string is obtained according to yyyy MM DD HH: mm: SS and the current time zone
Log.i("VU",DateUtils.dateTimeToGMT())
//Set the time zone as the East Sixth zone, and the time format is yyyy MM. dd HH:mm
Log.i("VU",DateUtils.dateTimeToGMT(GMT_PLUS_SIX,FORMAT_YYYY2MM2DD_HH_MM))
```

result:

```kotlin
// By default
2022-02-08 14:51:40.894 10129-10129/com.gcode.vastutils I/VU: 2022-02-08 14:51:40
// Set parameters
2022-02-08 14:54:35.201 11780-11780/com.gcode.vastutils I/VU: 2022.02.08 12:54
```

## Parse the current time according to the given UTC time and format

for example:

```kotlin
Log.i("VU",DateUtils.dateTimeFromGMT("07:01",FORMAT_HH_MM))
```

result:

```kotlin
2022-02-08 15:01:25.009 14700-14700/com.gcode.vastutils I/VU: 15:01
```

## Get the start (or end) time of the week. Monday is the first day

for example:

```kotlin
// Get start time
Log.i("VU",DateUtils.weekStartTime())
// Get end time
Log.i("VU",DateUtils.weekEndTime())
```

result:

```kotlin
//Get start time
2022-02-08 15:03:41.619 15780-15780/com.gcode.vastutils I/VU: 2022-02-07
//Get end time
2022-02-08 15:05:10.837 16168-16168/com.gcode.vastutils I/VU: 2022-02-13
```

## Get the timestamp of the beginning (or end) of the week. Sunday is the first day

for example:

```kotlin
// Start timestamp
Log.i("VU",DateUtils.getWeekStartTime())
// End timestamp
Log.i("VU",DateUtils.getWeekEndTime())
```

result:

```kotlin
// Start timestamp
2022-02-08 15:08:31.918 17680-17680/com.gcode.vastutils I/VU: 2022-02-06
// End timestamp
2022-02-08 15:09:47.869 18010-18010/com.gcode.vastutils I/VU: 2022-02-12
```