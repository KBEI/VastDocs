# DateUtils

## 支持的时间格式

```kotlin
const val DATE_FORMAT = "yyyy-MM-dd"
const val TIME_FORMAT = "yyyy-MM-dd HH:mm:ss"
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
const val FORMAT_MMCDD_HH_MM = "MM月dd日 HH:mm"
const val FORMAT_MMCDD = "MM月dd日"
const val FORMAT_YYYYCMMCDD = "yyyy年MM月dd日"
```

## 支持的时区

```kotlin
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

## 获取当前时间

示例代码

```kotlin
Log.i("VU",DateUtils.currentTime)
```

运行结果

```
// 默认按照 年月日-小时分钟秒结果
2022-02-08 12:34:15.921 11132-11132/com.gcode.vastutils I/VU: 2022-02-08 12:34:15
```

## 获取设备当前所在时区

示例代码

```kotlin
Log.i("VU",DateUtils.currentTimeZone)
```

运行结果

```
2022-02-08 12:39:07.938 13174-13174/com.gcode.vastutils I/VU: GMT+08:00
```

## 获取当前最小日期的Date对象

示例代码

```kotlin
val date: Date = DateUtils.minDate()
```

## 按照指定格式解析的最小日期字符串

示例代码

```kotlin
// 不添加参数，则默认按照yyyy-MM-dd HH:mm:ss的格式解析
Log.i("VU",DateUtils.minDateToString())
// 添加格式参数，只返回小时和分钟
Log.i("VU",DateUtils.minDateToString(FORMAT_HH_MM))
```

运行结果

```
// 默认格式
2022-02-08 14:20:30.002 17203-17203/com.gcode.vastutils I/VU: 1900-02-01 14:20:30
// 给定格式运行结果
2022-02-08 14:18:51.090 16270-16270/com.gcode.vastutils I/VU: 14:18
```

## 根据给定的时间字符串和格式获取Date对象

示例代码

```kotlin
val date: Date? = DateUtils.datetimeFromString("14:18", FORMAT_HH_MM)
```

## 将给定的Date解析为时间字符串

示例代码

```kotlin
// 获取一个Date对象
val date: Date? = DateUtils.datetimeFromString("14:18", FORMAT_HH_MM)
// 在日志中打印时间字符串
Log.i("VU",DateUtils.datetimeToString(date!!, FORMAT_HH_MM_SS))
```

运行结果

```
2022-02-08 14:40:07.019 2431-2431/com.gcode.vastutils I/VU: 14:18:00
```

## 根据给定的时区和时间格式返回对应的字符串

示例代码

```kotlin
// 默认情况下，按照yyyy-MM-dd HH:mm:ss和当前所处的时区获取字符串
Log.i("VU",DateUtils.dateTimeToGMT())
// 设置时区为东六区，时间格式为yyyy.MM.dd HH:mm
Log.i("VU",DateUtils.dateTimeToGMT(GMT_PLUS_SIX,FORMAT_YYYY2MM2DD_HH_MM))
```

运行结果

```kotlin
// 默认情况下
2022-02-08 14:51:40.894 10129-10129/com.gcode.vastutils I/VU: 2022-02-08 14:51:40
// 设置参数
2022-02-08 14:54:35.201 11780-11780/com.gcode.vastutils I/VU: 2022.02.08 12:54
```

## 根据给定的UTC时间和格式解析出当前时间

示例代码

```kotlin
Log.i("VU",DateUtils.dateTimeFromGMT("07:01",FORMAT_HH_MM))
```

运行结果

```
2022-02-08 15:01:25.009 14700-14700/com.gcode.vastutils I/VU: 15:01
```

## 获取本周开始(或结束)时间，周一是第一天

示例代码

```kotlin
// 获取开始时间
Log.i("VU",DateUtils.weekStartTime())
// 获取结束时间
Log.i("VU",DateUtils.weekEndTime())
```

运行结果

```
// 开始时间
2022-02-08 15:03:41.619 15780-15780/com.gcode.vastutils I/VU: 2022-02-07
// 结束时间
2022-02-08 15:05:10.837 16168-16168/com.gcode.vastutils I/VU: 2022-02-13
```

## 获取本周开始(或结束)的时间戳，周日是第一天

示例代码

```kotlin
// 开始时间戳
Log.i("VU",DateUtils.getWeekStartTime())
// 结束时间戳
Log.i("VU",DateUtils.getWeekEndTime())
```

运行结果

```
// 开始时间戳
2022-02-08 15:08:31.918 17680-17680/com.gcode.vastutils I/VU: 2022-02-06
// 结束时间戳
2022-02-08 15:09:47.869 18010-18010/com.gcode.vastutils I/VU: 2022-02-12
```