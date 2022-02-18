# BaseVastAdapter

> If possible, it is recommended to use **BaseVastBindingAdapter**

## Quick start

Through the following example,  you can quickly apply **BaseVastAdapter ** to your project

- First, we need your data class to implement the **VastAdapterItem** interface,Let's take **AExample **and **BExample** as examples.

```kotlin
// Vaapclickevent is your custom click event
// Vadplongclickevent is your custom long click event
// The return value of getvadpitemtype method should be the same as the corresponding VH
class AExample(
    val data: String,
    override var vAdpClickEvent: VAapClickEvent,
    override var vAdpLongClickEvent: VAdpLongClickEvent
):VastAdapterItem {
    override fun getVAdpItemType(): String {
        return "person"
    }
}

class BExample(
    val drawable:Int,
    override var vAdpClickEvent: VAapClickEvent,
    override var vAdpLongClickEvent: VAdpLongClickEvent
) : VastAdapterItem {
    override fun getVAdpItemType(): String {
        return "picture"
    }
}
```

- Set the corresponding viewholder, which needs to inherit from **BaseVastAdapterVH**

```kotlin
// VH corresponding to AExample
class AViewHolder(itemView: View): BaseVastAdapterVH(itemView) {
    private val tv:TextView

    override fun onBindData(item: VastAdapterItem) {
        super.onBindData(item)
        tv.text = (item as AExample).data
    }

    class Factory:BVAdpVHFactory{
        override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): BaseVastAdapterVH {
            return AViewHolder(LayoutInflater.from(parent.context).inflate(R.layout.item_textview,parent,false))
        }

        override fun getVAdpVHType(): String {
            return "person" // Consistent with Item
        }
    }

    init {
        tv = itemView.findViewById(R.id.text)
    }
}

//VH corresponding to BExample
class BViewHolder(itemView: View) : BaseVastAdapterVH(itemView) {

    private val iv: ImageView

    override fun onBindData(item: VastAdapterItem) {
        super.onBindData(item)
        iv.setImageResource((item as BExample).drawable)
    }

    class Factory : BVAdpVHFactory {

        override fun onCreateViewHolder(
            parent: ViewGroup,
            viewType: Int
        ): BaseVastAdapterVH {
            val inflater = LayoutInflater.from(parent.context)
            val itemView: View = inflater.inflate(R.layout.item_imageview, parent, false)
            return BViewHolder(itemView)
        }

        override fun getVAdpVHType(): String {
            return "picture"
        }

    }

    init {
        iv = itemView.findViewById(R.id.item_image)
    }
}
```

- Implement  Adapter

```kotlin
class BaseAdapter(
    private val items: MutableList<VastAdapterItem>,
    factories: MutableList<BaseVastAdapterVH.BVAdpVHFactory>
) : BaseVastAdapter(items, factories)
```

- Use in  MainActivity

```kotlin
// Get data source
private val datas:MutableList<VastAdapterItem> = ArrayList()

for(i in 0..10){
    datas.add(AExample(i.toString(),null,null))
    datas.add(BExample(R.drawable.ic_knots,null,null))
}

// Set to RecyclerView
adapter = BaseAdapter(datas, mutableListOf(AViewHolder.Factory(), BViewHolder.Factory()))

// Datarv is RecyclerView
dataRv.adapter = adapter
dataRv.layoutManager = LinearLayoutManager(this)
```

<div align="center"><img src="../assets/images/VastAdapter.gif" width=30%/></div>

## Add click (or long press) event

Click events are essential to a list. The following example shows you how to add corresponding click (or long press) events to an item

```kotlin
// Set click event
private val click:VAapClickEvent = { _: View, pos:Int,->
    showShortMsg("Click event and pos is $pos.")
}

// Set long press event
private val longClick:VAdpLongClickEvent = { _: View, pos:Int,->
    showShortMsg("Long click event and pos is $pos.")
    true
}

// Set the corresponding click event when adding a data source
for(i in 0..10){
    datas.add(AExample(i.toString(),click,null))
    datas.add(BExample(R.drawable.ic_knots,null,longClick))
}
```

<div align="center"><img src="../assets/images/VastAdapterClick.gif" width=30%/></div>

## Add new data type

If you want to add a third type of data to the list, you only need the following three steps

- Define a new data type, such as **CExample**，and make it implement the **VastAdapterItem**  interface
- Define the ViewHolder corresponding to **CExample**,such as **CViewHolder**
- Add its corresponding  **Factory** to the adapter

  ```kotlin
  adapter = BaseAdapter(datas, mutableListOf(AViewHolder.Factory(), BViewHolder.Factory() ,CViewHolder.Factory()))
  ```

## Add additional features to the adapter

The following example shows you how to add the function of judging whether the data source is empty to the Adapter

```kotlin
class BaseAdapter(
    private val items: MutableList<VastAdapterItem>,
    factories: MutableList<BaseVastAdapterVH.BVAdpVHFactory>
) : BaseVastAdapter(items, factories) {

    /**
     * Returns true if the collection is empty (does not contain any elements), otherwise false.
     * @return Boolean
     */
    fun isItemEmpty() = items.isEmpty()
}
```

## Quote

Part of the design of BaseVastAdapter refers to [completely decouple RecyclerView.Adapter](https://puke3615.github.io/2018/08/26/Android-RecyclerView-Architecture-Design/)

