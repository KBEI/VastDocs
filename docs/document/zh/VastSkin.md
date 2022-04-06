# VastSkin

`VastSkin` 是基于替换 [LayoutInflater.Factory2](https://developer.android.com/reference/android/view/LayoutInflater.Factory2) 实现的非侵入式换肤框架

## 快速开始

### 注册Application

```xml
<application
        android:name="com.gcode.vasttools.base.VastApp"
        ...>
</application>
```

如果你需要设置自己的Application，不过请确保其继承自 `VastApp`

### 将获取到的皮肤资源包加载即可

```kotlin
// 在Kotlin中调用
VastSkinManager.loadSkin("data/data/com.gcode.vastutils/files/darkskin-debug.apk")
```

```java
// 在java中调用
VastSkinManager.INSTANCE.loadSkin("data/data/com.gcode.vastutils/files/darkskin-debug.apk");
```

没错，就这么简单！

## 支持替换的资源标签

目前 `VastSkin` 支持替换以下资源:

```kotlin
internal const val CHANGEABLY_BACKGROUND = "background"
internal const val CHANGEABLY_SRC = "src"
internal const val CHANGEABLY_TEXT_COLOR = "textColor"
internal const val CHANGEABLY_DRAWABLE_LEFT = "drawableLeft"
internal const val CHANGEABLY_DRAWABLE_TOP = "drawableTop"
internal const val CHANGEABLY_DRAWABLE_RIGHT = "drawableRight"
internal const val CHANGEABLY_DRAWABLE_BOTTOM = "drawableBottom"
```