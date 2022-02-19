# VastTools

## Version 0.0.5

- [ ] 移除了 `CameraUtils` 工具类
- [ ] 移除了 `UrlValidator` 网络Url验证器
- [ ] `ScreenSizeUtils` 现在不再支持全面屏判断，只能获取屏幕的长宽
- [ ] 删除了 `AspectRatioDevice` ，不再支持定义更多的设备类型以及其对应的屏幕长宽比来判断全面屏
- [ ] `MsgWindowUtils` 不再支持弹出 `Dialog`
- [x] 新增 `ColorUtils` 工具类
- [x] 新增 `ShapeAndStateUtils` 工具类
- [x] 新增 `User` 和 `Response` 两个Bean
- [x] 优化了 `DateUtils` 工具类，修复了部分逻辑
- [x] `IntentUtils` 添加了 `resolveActivity` 判断，针对API 30以上的情况设定了提示信息
- [x] 修复日志打印logPrint函数存在的逻辑问题，删除了需要添加Class的环节，优化日志打印对于长度判断的设定，LogContent接口移动至 `LogUtils.kt` 内
- [x] `MsgWindowUtils` 更名为 `ToastUtils`

## Version 0.0.4

- [ ] `NoMatchAspectRatio` 异常
- [ ] `BuildVersionException` 异常
- [ ] 附带的140种颜色
- [x] 新增 `MergeBitmapUtils` BitMap合并工具类
- [x] 新增 `SystemUtils` 工具类
- [x] `DateFormat` 添加了常用的时间格式以及GMT时区
- [x] `DateFormatString` `GmtFormatString` `YearFormatString` 注解用来判断DateUtils内的参数类型
- [x] 完善 `DateUtils` 方法和注释
- [x] 全面屏判断由 `isAllScreenDevice` 根据 **Build.VERSION.SDK_INT** 选择对应的API，`isAllScreenDeviceApi31` ， `isAllScreenDeviceApi30` ，`isAllScreenDeviceApi30Down` 不可从外部调用
- [x] 屏幕高度获取由 `getMobileScreenHeight` 根据 **Build.VERSION.SDK_INT** 选择对应的API， `getMobileScreenHeightApi31` ，`getMobileScreenHeightApi30` ， `getMobileScreenHeightApi30Down` 不可从外部调用
- [x] 修复 `ScreenSizeUtils` 屏幕高度获取存在问题

## Version 0.0.3

- [x] 修复了日志打印不全解决的问题
- [x] 修复日志打印堆栈信息有时候存在不匹配问题
- [x] 支持定义更多的设备类型以及其对应的屏幕长宽比来判断全面屏

## Version 0.0.2

- [ ] 删除了Adapter部分

## Version 0.0.1

- [x] 将原本的代码由 `jitpack` 迁移至 `mavencentral` ，**该版本还包含Adapter部分**