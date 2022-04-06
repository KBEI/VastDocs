# SystemUtils

`Systemutils` provides you with some methods to get system information.

## Get system language

```kotlin
LogUtils.i("VU", systemLanguage)
```

```kotlin
2022-02-10 22:06:24.272 24641-24641/com.gcode.vastutils I/class (MainActivity.kt:52): zh
```

## Return an array of all installed locales

```kotlin
for(locale in systemLanguageList){
    // to do something
}
```

## Return the Android version of the system

```kotlin
LogUtils.i("VU", systemAndroidVersion)
```

```kotlin
2022-02-10 22:12:03.397 29894-29894/com.gcode.vastutils I/class (MainActivity.kt:52): 12
```

## Return the end user visible name of the end product

```kotlin
// This device is redmi K40
2022-02-10 22:15:53.820 4584-4584/com.gcode.vastutils I/class (MainActivity.kt:52): M2012K11AC
```

## Returns the consumer visible brand (if any) associated with the product / hardware

```kotlin
LogUtils.i("VU", deviceBrand)
```

```kotlin
2022-02-10 22:17:47.494 6086-6086/com.gcode.vastutils I/class (MainActivity.kt:52): Redmi
```