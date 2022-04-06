# VastBaseFragment

`VastBaseFragment` 是基于 [Fragment](https://developer.android.com/reference/androidx/fragment/app/Fragment.html) 进行封装的，同时基于 `VastBaseFragment` 又进行二次封装，如图所示：

<div align="center"><img src="../assets/images/vbf.png"></div>

## 快速使用

我们以 `VastVbVmFragment` 为例，向你展示了如何将其添加到你的项目当中：

```kotlin
class BaseVbFragment(override val layoutId: Int = 0) : VastVbVmFragment<FragmentBaseVbBinding, BaseVM>() {

    override fun initView(savedInstanceState: Bundle?) {
        mBinding.tv.setOnClickListener {
            ... //click event
        }
    }

}
```

注意，在此情况下你只需要给 `layoutId` 设定为默认值 0 即可。

当然，如果你的项目中没有采用 [ViewBinding](https://developer.android.com/topic/libraries/view-binding?hl=zh-cn) ，你可以继承 `VastVmFragment` ，在此情况下你需要将 `layoutId` 设定为对应的布局id，例如：

```kotlin
class BaseVmFragment(override val layoutId: Int = R.layout.fragment_base_vm) :VastVmActivity<BaseVM>() {

    override fun initView(savedInstanceState: Bundle?) {
        ... //Something to do
    }

}
```