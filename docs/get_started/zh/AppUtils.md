# AppUtils

## 获取应用包名

示例代码

```kotlin
Log.i("VU",getPackageName(this)?: "")
```

运行结果

```
2022-02-08 12:15:42.888 28668-28668/com.gcode.vastutils I/VU: com.gcode.vastutils
```

## 获取应用名

示例代码

```kotlin
Log.i("VU",getAppName(this)?: "")
```

运行结果

```
2022-02-08 12:16:34.509 29223-29223/com.gcode.vastutils I/VU: VastUtilsSampleDemo
```

## 获取版本名

示例代码

```kotlin
Log.i("VU",getVersionName(this)?: "")
```

运行结果

```
2022-02-08 12:21:32.561 586-586/com.gcode.vastutils I/VU: 1.0
```

## 获取版本号

示例代码

```kotlin
Log.i("VU", getVersionCode(this).toString())
```

运行结果

```
2022-02-08 12:24:11.924 6275-6275/com.gcode.vastutils I/VU: 1
```

## 判断应用是否是Debug状态

示例代码

```kotlin
Log.i("VU", getAppDebug(this).toString())
```

运行结果

```
2022-02-08 12:24:48.678 7578-7578/com.gcode.vastutils I/VU: true
```

## 获取应用图标

```kotlin
// iv是一个imageView控件
iv.setImageBitmap(getAppBitmap(this))
```

## build.gradle配置

```groovy
defaultConfig {
  applicationId "com.gcode.vastutils"
  ... //sdk version
  versionCode 1
  versionName "1.0"

  testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
}
```