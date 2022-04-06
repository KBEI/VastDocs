# ColorUtils

`ColorUtils` 为你提供了Color不同格式之间的转换方法

## 颜色十六进制字符串转换为Color int

```kotlin
val colorInt = colorHex2Int("#12c2e9")
```

## 颜色十六进制字符串转换为 RGB 数组

```kotlin
val rgb:IntArray = colorHex2RGB("#12c2e9")
```

## 颜色 int 转换为十六进制字符串

```kotlin
val colorHex:String = colorInt2Hex(-15547671)
```

## Color int 转换为 RGB 数组

```kotlin
val rgb:IntArray = colorInt2RGB(-15547671)
```

## RGB 数组转换为颜色十六进制字符串

```kotlin
val colorHex:String = colorRGB2Hex(intArrayOf(63,226,197))
```

## RGB 数组转换为Color int

```kotlin
val colorHex:Int = colorRGB2Int(intArrayOf(63,226,197))
```