# DensityUtils

`DensityUtils` provide you with some methods to convert different dimensions. For more information about dimensions, you can click [Dimension](https://developer.android.google.cn/guide/topics/resources/more-resources?hl=zh-cn#Dimension) to find out.

## Conversion between PX and DP

for example:

```kotlin
val dpValue = DensityUtils.px2dp(10f)

val pxValue = DensityUtils.dp2px(10f)
```

## Conversion between SP and PX

for example:

```kotlin
val spValue = DensityUtils.px2sp(10f)

val pxValue = DensityUtils.sp2px(10f)
```

## Conversion between SP and DP

for example:

```kotlin
val spValue = DensityUtils.dp2sp(10f)

val dpValue = DensityUtils.sp2dp(10f)
```

## Convert DP or SP to float

for example:

```kotlin
val spValue = 10f.sp

val dpValue = 10f.dp
```