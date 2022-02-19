# VastAdapter

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