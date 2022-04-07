# VastTools

## Version 0.0.7(Latest)

- [x] 修复 `LogUtils` 的 syncIsDeBug 方法被错误的加上了 internal 关键字的问题  [#issue 37](https://github.com/SakurajimaMaii/VastUtils/issues/37) 

## Version 0.0.6

- [ ] 删除了 `CheckPermission` 注解
- [ ] 删除了 `UnderTest` 注解
- [ ] 删除了 `ColorUtils` 颜色获取方法
- [x] 新增基于 [AppCompatActivity](https://developer.android.com/reference/androidx/appcompat/app/AppCompatActivity) 封装的 Activity 基类，目前有 `VastVbActivity` `VastVbVmActivity` `VastVmActivity`
- [x] 新增基于 [Fragment](https://developer.android.com/reference/androidx/fragment/app/Fragment.html) 封装的 Fragment 基类，目前有 `VastVbFragment` `VastVbVmFragment` `VastVmFragment`
- [x] 新增基于 [Factroy2](https://developer.android.com/reference/android/view/LayoutInflater.Factory2) 实现的 `VastSkin` 插件
- [x] 新增 `IDCardUtils` 工具类，提供中国居民身份证号码本地校验
- [x] 新增 `RegexUtils` 工具类，提供了一些字符串格式正则检查
- [x] `DensityUtils` 新增 `.px` `.pt` `.mm` `.inches` 拓展方法
- [x] `IntentUtils` 新增 [RequiresPermission](https://developer.android.com/studio/write/annotations?hl=zh-cn#permissions) 来检查权限
- [x] 优化 `Response` 设计，将 `data` 部分改进为泛型
- [x] 修复 `LogUtils` 日志工具类由于使用 `BuildConfig.DEBUG` 而导致的不打印日志的问题 [#issue 33](https://github.com/SakurajimaMaii/VastUtils/issues/33)
- [x] 修复 `ScreenSizeUtils` 横屏模式下获取到的宽度出错问题 [#issue 34](https://github.com/SakurajimaMaii/VastUtils/issues/34) 

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