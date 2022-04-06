# ColorUtils

`ColorUtils` provides you with conversion methods between different Color formats

## Color hexadecimal string convert to int

```kotlin
val colorInt = colorHex2Int("#12c2e9")
```

## Color hexadecimal string convert to an array of RGB

For example,it will convert **#12c2e9** to **{18,194,233}**

```kotlin
val rgb:IntArray = colorHex2RGB("#12c2e9")
```

## Color int convert to hexadecimal string

```kotlin
val colorHex:String = colorInt2Hex(-15547671)
```

## Color int convert to an array of RGB

```kotlin
val rgb:IntArray = colorInt2RGB(-15547671)
```

## An array of RGB convert to color hexadecimal string

For example,it will convert **{63,226,197}** to **#3FE2C5**

```kotlin
val colorHex:String = colorRGB2Hex(intArrayOf(63,226,197))
```

## An array of RGB convert to color int.

```kotlin
val colorHex:Int = colorRGB2Int(intArrayOf(63,226,197))
```