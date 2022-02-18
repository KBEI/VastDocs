# BaseVastBindAdapter

## Quick start

Through the following example, you can quickly apply **BaseVastBindAdapter**  to your project

- First, we need your data class to implement the **VastBindAdapterItem** interface. Let's take **Person** and **Picture** as examples.

```kotlin
// getVBAdpItemType returns the corresponding layout id
data class Person(
    val firstName: String, val lastName: String,
    override var vbAdpClickEvent: VAapClickEvent,
    override var vbAdpLongClickEvent: VAdpLongClickEvent,
) : VastBindAdapterItem {

    override fun getVBAdpItemType(): Int {
        return R.layout.item_bind_textview
    }

}

data class Picture(
    val drawable: Int,
    override var vbAdpClickEvent: VAapClickEvent,
    override var vbAdpLongClickEvent: VAdpLongClickEvent,
) : VastBindAdapterItem {

    override fun getVBAdpItemType(): Int {
        return R.layout.item_bind_imageview
    }

}
```

- Edit the corresponding layout

**Note that the name in the variable in all data layout files in the list must be the same, for example, it is item here**

```xml
// Layout corresponding to Person
<?xml version="1.0" encoding="utf-8"?>
<layout>
    <data>
        <variable
            name="item"
            type="com.gcode.vastutils.basebindadpexample.model.Person" />
    </data>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:text="@{item.firstName}"/>
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:text="@{item.lastName}"/>
    </LinearLayout>
</layout>

//Layout corresponding to Picture
<?xml version="1.0" encoding="utf-8"?>
<layout>
    <data>
        <variable
            name="item"
            type="com.gcode.vastutils.basebindadpexample.model.Picture" />
    </data>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">
        <ImageView
            android:id="@+id/item_image"
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:src="@{item.drawable}"
            android:contentDescription="@string/picture"
            android:layout_gravity="center_horizontal"/>
    </LinearLayout>
</layout>
```

- Implement Adapter

```kotlin
class BaseBindingAdapter(
    private val dataSource:MutableList<VastBindAdapterItem>
):BaseVastBindAdapter(dataSource){

    override fun setVariableId(): Int {
        return BR.item
    }

}
```

- Use in  Activity

```kotlin
private val datas:MutableList<VastBindAdapterItem> = ArrayList()

for(i in 0..10){
    datas.add(Person(i.toString(),i.toString(),null,null))
    datas.add(Picture(R.drawable.ic_knots,null,null))
}

// Set to RecyclerView
val adapter = BaseBindingAdapter(datas)
dataRv.adapter = adapter
dataRv.layoutManager = LinearLayoutManager(this)
```

<div align="center"><img src="../assets/images/VastAdapter.gif" width=30%/></div>

## Add click (or long press) event

Click events are essential to a list. The following example shows you how to add corresponding click (or long press) events to an item

```kotlin
// Set click event
private val click:VAapClickEvent = { _: View, pos:Int->
    showShortMsg("Hello,User.And position is $pos")
}

private val longClick:VAdpLongClickEvent = { _: View, pos:Int->
    showShortMsg("Hello,User.And position is $pos")
    true
}

// Set the corresponding click event when adding a data source
for(i in 0..10){
    datas.add(Person(i.toString(),i.toString(),click,null))
    datas.add(Picture(R.drawable.ic_knots,null,longClick))
}
```

<div align="center"><img src="../assets/images/VastAdapterClick.gif" width=30%/></div>

## Add additional features to the  Adapter

The following example shows you how to add the function of judging whether the data source is empty to the Adapter

```kotlin
class BaseBindingAdapter(
    private val dataSource:MutableList<VastBindAdapterItem>
):BaseVastBindAdapter(dataSource) {

    /**
     * Returns true if the collection is empty (does not contain any elements), otherwise false.
     * @return Boolean
     */
    fun isItemEmpty() = items.isEmpty()

    override fun setVariableId(): Int {
        return BR.item
    }

}
```

Of course, you can also refer to the example application

## The use of @BindingAdapter

When using DataBinding, sometimes we need to customize some content. The following example shows you how to use @BindingAdapter in BaseVastBindAdapter.

Let's take **android:src** as an example

```kotlin
class BaseBindingAdapter(
    private val dataSource:MutableList<VastBindAdapterItem>
):BaseVastBindAdapter(dataSource) {
    companion object {
        @JvmStatic @BindingAdapter("android:src")
        fun setImageUri(view: ImageView, imageUri: String?) {
            if (imageUri == null) {
                view.setImageURI(null)
            } else {
                view.setImageURI(Uri.parse(imageUri))
            }
        }
    }

    override fun setVariableId(): Int {
        return BR.item
    }

}
```