# VastTools

## Version 0.0.5

- [ ] 移除了 `CameraUtils` 工具类
- [ ] 移除了 `UrlValidator` 网络Url验证器
- [ ] `ScreenSizeUtils` 现在不再支持全面屏判断，只能获取屏幕的长宽
- [ ] 删除了 `AspectRatioDevice`
- [ ] `MsgWindowUtils` 不再支持弹出 `Dialog`
- [x] 新增 `ColorUtils` 工具类
- [x] 新增 `ShapeAndStateUtils` 工具类
- [x] 新增 `User` 和 `Response` 两个Bean
- [x] 优化了 `DateUtils` 工具类，修复了部分逻辑
- [x] `IntentUtils` 添加了 `resolveActivity` 判断，针对API 30以上的情况设定了提示信息
- [x] 修复日志打印logPrint函数存在的逻辑问题，删除了需要添加Class的环节，优化日志打印对于长度判断的设定，LogContent接口移动至 `LogUtils.kt` 内
- [x] `MsgWindowUtils` 更名为 `ToastUtils`