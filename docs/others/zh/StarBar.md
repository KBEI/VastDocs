# StarBar

## xml布局

```xml
<com.gcode.widget.StarBarView
    android:id="@+id/sbv_starbar_2"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:star_space_width="1dp"
    app:star_height="25dp"
    app:star_normal="@mipmap/ic_star_yellow_normal"
    app:star_select_method="star_sliding_operation"
    app:star_max="5"
    app:star_orientation="star_horizontal"
    app:star_rating="2.5"
    app:star_selected="@mipmap/ic_star_yellow_selected"
    app:star_width="25dp"
    android:layout_marginTop="66dp" />
```

## 代码使用

```kotlin
mStarbar.apply {
    getStarRating()
    setStarSelectedBitmap(R.drawable.ic_star_dark_blue_selected)
    setStarNormalBitmap(R.drawable.ic_star_dark_blue_normal)
    setStarMaxNumber(5)
    setStarBitMapSize(40,40)
    setStarSpaceWidth(20)
    setStarSelectMethod(StarBarSelectMethod.SlidingOperation)
    try {
        setStarRating(3.6f)
    }catch (e: StarBarException){
        e.printStackTrace()
    }
}
```