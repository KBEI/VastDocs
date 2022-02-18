# DensityUtils

尺寸工具类为大家提供了一些基本的尺寸间的相互转换，关于尺寸的更多信息，你可以点击[Dimension](https://developer.android.google.cn/guide/topics/resources/more-resources?hl=zh-cn#Dimension)进行了解

## px和dp之间相互转换

示例代码

```kotlin
val dpValue = DensityUtils.px2dp(10f)

val pxValue = DensityUtils.dp2px(10f)
```

## sp和px之间的转换

```kotlin
val spValue = DensityUtils.px2sp(10f)

val pxValue = DensityUtils.sp2px(10f)
```

## sp和dp之间的转换

```kotlin
val spValue = DensityUtils.dp2sp(10f)

val dpValue = DensityUtils.sp2dp(10f)
```

## 将dp或者sp转换为float

```kotlin
val spValue = 10f.sp

val dpValue = 10f.dp
```