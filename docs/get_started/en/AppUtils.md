# AppInfoUtils

## Get app package name

for example:

```kotlin
Log.i("VU",getPackageName(this)?: "")
```

result:

```
2022-02-08 12:15:42.888 28668-28668/com.gcode.vastutils I/VU: com.gcode.vastutils
```

## Get the application name

for example:

```kotlin
Log.i("VU",getAppName(this)?: "")
```

result:

```
2022-02-08 12:16:34.509 29223-29223/com.gcode.vastutils I/VU: VastUtilsSampleDemo
```



## Get version name

for example:

```kotlin
Log.i("VU",getVersionName(this)?: "")
```

result:

```
2022-02-08 12:21:32.561 586-586/com.gcode.vastutils I/VU: 1.0
```

## Get version number

for example:

```kotlin
Log.i("VU", getVersionCode(this).toString())
```

result:

```
2022-02-08 12:24:11.924 6275-6275/com.gcode.vastutils I/VU: 1
```

## Determine whether the application is in debug state

for example:

```kotlin
Log.i("VU", getAppDebug(this).toString())
```

result:

```
2022-02-08 12:24:48.678 7578-7578/com.gcode.vastutils I/VU: true
```

## Get app Icon

```kotlin
// ivI is an ImageView control
iv.setImageBitmap(getAppBitmap(this))
```

## Configuration of build. Gradle 

```groovy
defaultConfig {
  applicationId "com.gcode.vastutils"
  ... //sdk version
  versionCode 1
  versionName "1.0"

  testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
}
```