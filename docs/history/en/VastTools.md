# VastTools

## Version 0.0.5

- [ ] Removed `CameraUtils` utility class
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