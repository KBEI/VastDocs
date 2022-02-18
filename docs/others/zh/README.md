# 其他库

## StarBar

一款自定义的安卓评分控件

- [x] 支持三种操作 `Unable 不可操作` `Click 整数点击` `Sliding 滑动`
- [x] 支持两种布局方式 `水平放置` `垂直放置`
- [x] 支持自定义星星选中和未选中图片
- [x] 支持自定义星星数量
- [x] 支持自定义星星图片尺寸

```groovy
// Add it in your root build.gradle at the end of repositories:
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}

// Add the dependency
implementation 'com.github.SakurajimaMaii:StarBar:0.0.5'
```

## ShapeButton

一款支持自定义的安卓按钮控件

- [x] 支持四种按钮类型 `圆形/椭圆形按钮` `矩形按钮` `圆角矩形按钮` `任意圆角矩形按钮`
- [x] 支持自定义按钮尺寸
- [x] 支持自定义按钮边框宽度以及颜色
- [x] 支持自定义按钮圆角半径
- [x] 支持自定义按钮填充色 `是否填充` `是否采用渐变填充`
- [x] 支持自定义渐变填充色以及角度
- [x] 支持自定义不同按钮状态下的背景色以及边框颜色

```groovy
// Add it in your root build.gradle at the end of repositories:
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}

// Add the dependency
implementation 'com.github.SakurajimaMaii:ShapeButton:0.0.5'
```