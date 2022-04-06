# VastNetStateLayout

## Quick start

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
        <!--content-->
    </com.gcode.vastnetstatelayout.view.VastNetStateLayout>
</androidx.constraintlayout.widget.ConstraintLayout>
```

## Change page state

`VastNetStateLayout` provides you with **four** page states for you to switch to

```kotlin
// show loading
netStateLayout.showLoading()
// show loading error
netStateLayout.showLoadingError()
// show empty data
netStateLayout.showEmptyData()
// show net error
netStateLayout.showNetError()
```

When the load is successful, you can use the following methods to display the correct page

```kotlin
netStateLayout.showSuccess()
```

## Set page event

`VastNetStateLayout` allows you to customize page click events

### Net error

```kotlin
vastNetStateMgr.setNetErrorListener(object :VastNetErrorListener{
    override fun onNetWorkError() {
        // Something to do when network error
    }
})
```

### Empty data

```kotlin
vastNetStateMgr.setEmptyDataListener(object :VastEmptyDataListener{
    override fun onEmptyData() {
        // Something to do when empty data
    }
})
```

### Loading error

```kotlin
vastNetStateMgr.setLoadingErrorListener(object :VastLoadingErrorListener{
    override fun onLoadingError() {
        // Something to do when loading error
    }
})
```

### Loading

```kotlin
vastNetStateMgr.setLoadingListener(object : VastLoadingListener {
    override fun onLoading() {
        // Something to do when loading
    }
})
```

## Custom page view

```kotlin
vastNetStateMgr.setNetErrorView(R.layout.error_page)
```