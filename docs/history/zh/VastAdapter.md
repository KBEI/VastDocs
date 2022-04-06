# VastAdapter

## Version 0.0.4

- [ ] 删除 `VastAdapterNotFound` 异常类
- [ ] 删除 `VastAdapterValueError` 异常类
- [x] `BaseVastAdapter` 更名为 `VastAdapter`
- [x] `BaseVastAdapterVH` 更名为 `VastAdapterVH` 
- [x] `BaseVastBindAdapter` 更名为 `VastBindAdapter` 
- [x] 新增 `VastAdapter` 通用点击事件 [#issue 36](https://github.com/SakurajimaMaii/VastUtils/issues/36)
- [x] 优化 `VastAdapter` 点击事件设计 [#issue 35](https://github.com/SakurajimaMaii/VastUtils/issues/35)
- [x] 修复 `VastAdapter` 长点击事件返回值的问题 [#issue 31](https://github.com/SakurajimaMaii/VastUtils/issues/31)

## Version 0.0.3

- [ ] 删除了 `BaseVastAdapter` 自带的增删改查逻辑
- [ ] 删除了 `BaseVastBindAdapter` 自带的增删改查逻辑
- [x] 现在支持针对不同类型的item设置不同的点击事件
- [x] `BaseVastAdapter` 现在支持快速添加新类型的VH
- [x] 优化了点击事件接口设计
- [x] `BaseVastAdapter` 修复了 `getItemViewType` 内的逻辑错误
- [x] 对 `onBindViewHolder` `onCreateViewHolder` `getItemViewType` `getItemCount` 这几个方法添加 final 限制

## Version 0.0.2

- [x] `BaseGcodeAdapter` 更名为 `BaseVastAdapter`
- [x] `BaseGcodeBindingAdapter` 更名为 `BaseVastBindingAdapter`
- [x] `BaseGcodeItem` 更名为 `BaseVastItem`

## Version 0.0.1

- [x] Adapter分离出来的第一个正式版