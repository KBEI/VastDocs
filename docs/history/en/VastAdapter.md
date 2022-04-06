# VastAdapter

## Version 0.0.4

- [ ] Delete `VastAdapterNotFound`
- [ ] Delete `VastAdapterValueError`
- [x] `BaseVastAdapter` renamed to `VastAdapter`
- [x] `BaseVastAdapterVH` renamed to `VastAdapterVH`
- [x] `BaseVastBindAdapter` renamed to `VastBindAdapter`
- [x] Added `VastAdapter` generic click event [#issue 36](https://github.com/SakurajimaMaii/VastUtils/issues/36)
- [x] Optimize `VastAdapter` click event design [#issue 35](https://github.com/SakurajimaMaii/VastUtils/issues/35)
- [x] Fix `VastAdapter` long click event return value issue [#issue 31](https://github.com/SakurajimaMaii/VastUtils/issues/31)

## Version 0.0.3

- [ ] Deleted the logic of adding, deleting, modifying and checking in `BaseVastAdapter`
- [ ] Deleted the logic of adding, deleting, modifying and checking in `BaseVastBindAdapter`
- [x] Now support setting different click events for different types of items
- [x] `BaseVastAdapter` now supports quick addition of new types of VH
- [x] Optimized click event interface design
- [x] `BaseVastAdapter` fixed logic error inside `getItemViewType`
- [x] Add final restrictions to `onBindViewHolder` `onCreateViewHolder` `getItemViewType` `getItemCount`

## Version 0.0.2

- [x] `BaseGcodeAdapter` renamed to `BaseVastAdapter`
- [x] `BaseGcodeBindingAdapter` renamed to `BaseVastBindingAdapter`
- [x] `BaseGcodeItem` renamed to `BaseVastItem`

## Version 0.0.1

- [x] The first official version of Adapter separated