# VastTools

## Version 0.0.7(Latest)

- [x] Fix `LogUtils` syncIsDeBug method is wrongly added internal keyword [#issue 37](https://github.com/SakurajimaMaii/VastUtils/issues/37)

## Version 0.0.6

- [ ] Removed `CheckPermission`
- [ ] Removed `UnderTest`
- [ ] Removed `ColorUtils` color get method
- [x] Added Activity base class based on [AppCompatActivity](https://developer.android.com/reference/androidx/appcompat/app/AppCompatActivity) package, currently there are `VastVbActivity` `VastVbVmActivity` `VastVmActivity`
- [x] Added Fragment base class based on [Fragment](https://developer.android.com/reference/androidx/fragment/app/Fragment.html) package, currently there are `VastVbFragment` `VastVbVmFragment` `VastVmFragment`
- [x] Added `VastSkin` plugin based on [Factroy2](https://developer.android.com/reference/android/view/LayoutInflater.Factory2)
- [x] Added `IDCardUtils` tool class to provide local verification of Chinese resident ID numbers
- [x] Added `RegexUtils` tool class, which provides some string format regularity checks
- [x] `DensityUtils` added `.px` `.pt` `.mm` `.inches` extension methods
- [x] `IntentUtils` added [RequiresPermission](https://developer.android.com/studio/write/annotations?hl=en-us#permissions) to check permissions
- [x] Optimized `Response` design, improved the `data` part to be generic
- [x] Fixed `LogUtils` log utility class not printing logs due to using `BuildConfig.DEBUG` [#issue 33](https://github.com/SakurajimaMaii/VastUtils/issues/33)
- [x] Fix `ScreenSizeUtils` width error in landscape mode [#issue 34](https://github.com/SakurajimaMaii/VastUtils/issues/34)

## Version 0.0.5

- [ ] Removed `CameraUtils`
- [ ] Removed `UrlValidator` web Url validator
- [ ] `ScreenSizeUtils` now no longer supports full screen judgment, only the length and width of the screen can be obtained
- [ ] Deleted `AspectRatioDevice` , no longer supports defining more device types and their corresponding screen aspect ratios to judge full screen
- [ ] `MsgWindowUtils` no longer supports popup `Dialog`
- [x] Added `ColorUtils` utility class
- [x] Added `ShapeAndStateUtils` utility class
- [x] Added `User` and `Response` beans
- [x] Optimized `DateUtils` utility class and fixed some logic
- [x] `IntentUtils` added `resolveActivity` judgment, and set prompt information for API 30 and above
- [x] Fixed the logical problem in the logPrint function of log printing, deleted the link that needs to add a Class, optimized the setting of the length judgment of log printing, and moved the LogContent interface to `LogUtils.kt`
- [x] `MsgWindowUtils` renamed to `ToastUtils`

## Version 0.0.4

- [ ] Delete `NoMatchAspectRatio` exception
- [ ] Delete `BuildVersionException` exception
- [ ] Delete 140 colors included
- [x] Added `MergeBitmapUtils` BitMap merge tool class
- [x] Added `SystemUtils` utility class
- [x] `DateFormat` adds common time formats and GMT time zone
- [x] `DateFormatString` `GmtFormatString` `YearFormatString` annotation is used to determine the parameter type in DateUtils
- [x] Improve `DateUtils` methods and annotations
- [x] For full screen judgment, `isAllScreenDevice` selects the corresponding API according to **Build.VERSION.SDK_INT**, `isAllScreenDeviceApi31` , `isAllScreenDeviceApi30` , `isAllScreenDeviceApi30Down` cannot be called from outside
- [x] The screen height is obtained by `getMobileScreenHeight` according to **Build.VERSION.SDK_INT** select the corresponding API, `getMobileScreenHeightApi31` , `getMobileScreenHeightApi30` , `getMobileScreenHeightApi30Down` be called from outside
- [x] Fix `ScreenSizeUtils` screen height acquisition problem

## Version 0.0.3

- [x] Fixed the problem of incomplete log printing
- [x] Fix log printing stack information sometimes mismatch problem
- [x] Support to define more device types and their corresponding screen aspect ratios to judge the full screen

## Version 0.0.2

- [ ] Removed Adapter section

## Version 0.0.1

- [x] Migrate the original code from `jitpack` to `mavencentral`, **this version also includes the Adapter part**