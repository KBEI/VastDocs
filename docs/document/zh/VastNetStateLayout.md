# VastNetStateLayout

## 布局使用

```xml
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".activity.NetStateActivity">
    <com.gcode.vastnetstatelayout.view.VastNetStateLayout
        android:id="@+id/net_state_layout"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
        <!--页面其他内容-->
    </com.gcode.vastnetstatelayout.view.VastNetStateLayout>
</androidx.constraintlayout.widget.ConstraintLayout>
```

## 切换页面状态

VastNetStateLayout为你提供了**四**种页面状态供你切换使用

```kotlin
// 展示网络加载页面
netStateLayout.showLoading()
// 展示网络加载错误页面
netStateLayout.showLoadingError()
// 展示空数据页面
netStateLayout.showEmptyData()
// 展示网络错误页面
netStateLayout.showNetError()
```

当加载成功时，你可以使用下列方式来显示正确的页面

```kotlin
netStateLayout.showSuccess()
```

## 设置页面事件

VastNetStateLayout允许你自定义页面点击事件

### 针对网络错误状态

```kotlin
vastNetStateMgr.setNetErrorListener(object :VastNetErrorListener{
    override fun onNetWorkError() {
        // Something to do when network error
    }
})
```

### 针对空数据状态

```kotlin
vastNetStateMgr.setEmptyDataListener(object :VastEmptyDataListener{
    override fun onEmptyData() {
        // Something to do when empty data
    }
})
```

### 针对加载错误状态

```kotlin
vastNetStateMgr.setLoadingErrorListener(object :VastLoadingErrorListener{
    override fun onLoadingError() {
        // Something to do when loading error
    }
})
```

### 针对加载状态

```kotlin
vastNetStateMgr.setLoadingListener(object : VastLoadingListener {
    override fun onLoading() {
        // Something to do when loading
    }
})
```

## 自定义页面背景

VastNetStateLayout允许你自定义状态页面，我们以自定义网络错误页面为示例

```kotlin
vastNetStateMgr.setNetErrorView(R.layout.error_page)
```