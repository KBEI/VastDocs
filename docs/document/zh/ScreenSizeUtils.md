# ScreenSizeUtils

`ScreenSizeUtils` 为你提供了获取屏幕长宽的方法，例如:

当你在 `Activity` 内使用时：

```kotlin
val screenWidth = getMobileScreenWidth()
val screenHeight = getMobileScreenHeight()
```

当你在 `Fragment` 内使用时

```kotlin
val screenHeight = requireContext().getMobileScreenHeight()
val screenWidth = requireContext().getMobileScreenWidth()
```

运行示例

```kotlin
LogUtils.i("VU","$screenWidth $screenHeight")

2022-02-10 21:47:37.265 4463-4463/com.gcode.vastutils I/class (MainActivity.kt:43): method: onCreate() key: VU content: 1080 2340
```