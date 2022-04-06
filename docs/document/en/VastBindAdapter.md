# VastBindAdapter

## Quick start

Through the following example, you can quickly apply `BaseVastBindAdapter` to your project

### Implement VastBindAdapterItem

Make sure that data class to implement the `VastBindAdapterItem` . Let's take a look at the `Person` and `Picture` .

```kotlin
// Use in kotlin
class Person(
    val firstName: String, val lastName: String,
    var vbAdpClickEventListener: VAapClickEventListener? = null,
    var vbAdpLongClickEventListener: VAdpLongClickEventListener? = null,
) :VastBindAdapterItem {

    override fun setVBAapClickEventListener(l: VAapClickEventListener?) {
        vbAdpClickEventListener = l
    }

    override fun getVBAapClickEventListener(): VAapClickEventListener? {
        return vbAdpClickEventListener
    }

    override fun setVBAdpLongClickEventListener(l: VAdpLongClickEventListener?) {
        vbAdpLongClickEventListener = l
    }

    override fun getVBAdpLongClickEventListener(): VAdpLongClickEventListener? {
        return vbAdpLongClickEventListener
    }

    override fun getVBAdpItemType(): Int {
        return R.layout.item_bind_textview
    }

}
```

```java
// Use in java
public class Picture implements VastBindAdapterItem {

    private int drawable;
    private VAapClickEventListener clickEventListener;
    private VAdpLongClickEventListener longClickEventListener;

    public Picture(int drawable, VAapClickEventListener clickEventListener, VAdpLongClickEventListener longClickEventListener) {
        this.drawable = drawable;
        this.clickEventListener = clickEventListener;
        this.longClickEventListener = longClickEventListener;
    }

    public int getDrawable() {
        return drawable;
    }

    public void setDrawable(int drawable) {
        this.drawable = drawable;
    }
    
    @Override
    public int getVBAdpItemType() {
        return R.layout.item_bind_imageview;
    }

    @Override
    public void setVBAapClickEventListener(@Nullable VAapClickEventListener l) {
        clickEventListener = l;
    }

    @Nullable
    @Override
    public VAapClickEventListener getVBAapClickEventListener() {
        return clickEventListener;
    }

    @Override
    public void setVBAdpLongClickEventListener(@Nullable VAdpLongClickEventListener l) {
        longClickEventListener = l;
    }

    @Nullable
    @Override
    public VAdpLongClickEventListener getVBAdpLongClickEventListener() {
        return longClickEventListener;
    }
}
```

### Layout

For elements in the same list, when you bind them into the corresponding layout using the `data` tag, their `name` fields should be the same.

For example: `Person` and `Picture` are in the same list, and their `name` fields in their layout files are both `item` .

```xml
// Person layout
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
```

```xml
// Picture layout
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

### Adapter

Make sure that the adapter implements `BaseVastBindAdapter`

```kotlin
// Use in kotlin
class BaseBindingAdapter(
    private val dataSource:MutableList<VastBindAdapterItem>
):BaseVastBindAdapter(dataSource){

    override fun setVariableId(): Int {
        return BR.item
    }

}
```

```java
// Use in java
public class BaseBindAdapter extends VastBindAdapter {
    public BaseBindAdapter(@NonNull List<VastBindAdapterItem> dataSource) {
        super(dataSource);
    }

    @Override
    public int setVariableId() {
        return BR.item;
    }
}
```

- Use in  Activity

```kotlin
// Use in kotlin
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

```java
// Use in java
private ArrayList<VastBindAdapterItem> datas = new ArrayList<>();

for (int i = 0; i < 10; i++) {
    datas.add(new Picture(R.drawable.ic_knots, null, null));
}

// 设置给RecyclerView
BaseBindAdapter adapter = new BaseBindAdapter(datas);
dataRv.setAdapter(adapter);
dataRv.setLayoutManager(new LinearLayoutManager(this));
```

<div align="center"><img src="../assets/images/VastAdapter.gif" width=30%/></div>

## Add click (or long press) event

For lists, click events are essential. `VastBindAdapter` supports you to set generic click events for lists. Of course, because your class implements the `VastBindAdapterItem` interface, you can also set click events for them individually.

### Generic click event settings

```kotlin
// Use in kotlin
adapter.setOnItemClickListener(object :VastBindAdapter.OnItemClickListener{
            override fun onItemClick(view: View, position: Int) {
                // Something you want to do
            }
        })
adapter.setOnItemLongClickListener(object :VastBindAdapter.OnItemLongClickListener{
            override fun onItemLongClick(view: View, position: Int): Boolean {
                // Something you want to do
                return true
            }
        })
```

```java
// Use in java
adapter.setOnItemClickListener((view, position) -> {
            // Something you want to do
        });
adapter.setOnItemLongClickListener((view, position) -> {
            // Something you want to do
            return true;
        });
```

### Set up individual click events

Note that if you define a click event for an item, it no longer supports generic click events.

```kotlin
// Use in kotlin
val click = object :VAapClickEventListener{
    override fun vAapClickEvent(view: View, pos: Int) {
        showShortMsg("Hello,User.And position is $pos")
    }
}

for(i in 0..10){
    datas.add(Person(i.toString(),i.toString(),click,null))
    datas.add(Picture(R.drawable.ic_knots,null,longClick))
}
```

```java
// Use in java
VAapClickEventListener click = (view, pos) -> {
    ToastUtils.showShortMsg(this,"Hello");
};

// 在设置数据源的时候设置
for (int i = 0; i < 10; i++) {
    datas.add(new Picture(R.drawable.ic_knots, click, null));
}
```

<div align="center"><img src="../assets/images/VastAdapterClick.gif" width=30%/></div>

## Add additional features to the  Adapter

The following example shows you how to add the function of judging whether the data source is empty to the Adapter

```kotlin
// Use in kotlin
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

```java
// Use in java
public class BaseBindAdapter extends VastBindAdapter {
    private ArrayList<VastBindAdapterItem> datas;

    public BaseBindAdapter(@NonNull List<VastBindAdapterItem> dataSource) {
        super(dataSource);
        datas.addAll(dataSource);
    }

    @Override
    public int setVariableId() {
        return BR.item;
    }

    public Boolean isEmpty(){
        return datas.isEmpty();
    }

}
```

Of course, you can also refer to the example application

## Binding adapters

When using DataBinding, sometimes we need to customize some content. The following example shows you how to use `@BindingAdapter` in `VastBindAdapter`.

Please click [Binding adapters](https://developer.android.google.cn/topic/libraries/data-binding/binding-adapters) to learn more about binding adapters.

```kotlin
// Use in kotlin
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

```java
// Use in java
public class BaseBindAdapter extends VastBindAdapter {

    @BindingAdapter("drawableStartCompat")
    public static void loadImage(TextView tv, int resId) {
        Drawable drawable = ResourcesCompat.getDrawable(App.context.getResources(),resId,null);
        tv.setCompoundDrawablesWithIntrinsicBounds(drawable,null,null,null);
    }
    
    private ArrayList<VastBindAdapterItem> datas;

    public BaseBindAdapter(@NonNull List<VastBindAdapterItem> dataSource) {
        super(dataSource);
        datas.addAll(dataSource);
    }

    @Override
    public int setVariableId() {
        return BR.item;
    }

    public Boolean isEmpty(){
        return datas.isEmpty();
    }

}
```