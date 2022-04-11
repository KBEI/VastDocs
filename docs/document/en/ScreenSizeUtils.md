# ScreenSizeUtils

Screensizeutils provides you with ways to get the length and width of the screen.

Use in `Activity` :

```kotlin
val screenWidth = getMobileScreenWidth()
val screenHeight = getMobileScreenHeight()
```

Use in `Fragment` :

```kotlin
val screenHeight = requireContext().getMobileScreenHeight()
val screenWidth = requireContext().getMobileScreenWidth()
```

For example:

```kotlin
LogUtils.i("VU","$screenWidth $screenHeight")

2022-02-10 21:47:37.265 4463-4463/com.gcode.vastutils I/class (MainActivity.kt:43): method: onCreate() key: VU content: 1080 2340
```