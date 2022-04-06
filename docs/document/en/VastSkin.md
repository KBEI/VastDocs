# VastSkin

`VastSkin` is a non-intrusive skinning framework based on the replacement [LayoutInflater.Factory2](https://developer.android.com/reference/android/view/LayoutInflater.Factory2)

## Quick start

### Register Application

```xml
<application
        android:name="com.gcode.vasttools.base.VastApp"
        ...>
</application>
```

If you need to set up your own Application, make sure it inherits from `VastApp`

### Loading skin resource

```kotlin
// Use in kotlin
VastSkinManager.loadSkin("data/data/com.gcode.vastutils/files/darkskin-debug.apk")
```

```java
// Use in java
VastSkinManager.INSTANCE.loadSkin("data/data/com.gcode.vastutils/files/darkskin-debug.apk");
```

Yes, it's that simple!

## Support src tag

Currently `VastSkin` supports replacing the following resources:

```kotlin
internal const val CHANGEABLY_BACKGROUND = "background"
internal const val CHANGEABLY_SRC = "src"
internal const val CHANGEABLY_TEXT_COLOR = "textColor"
internal const val CHANGEABLY_DRAWABLE_LEFT = "drawableLeft"
internal const val CHANGEABLY_DRAWABLE_TOP = "drawableTop"
internal const val CHANGEABLY_DRAWABLE_RIGHT = "drawableRight"
internal const val CHANGEABLY_DRAWABLE_BOTTOM = "drawableBottom"
```