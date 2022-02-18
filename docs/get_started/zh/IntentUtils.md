# IntentUtils

`IntentUtils` 为你提供了一些常见[Intent](https://developer.android.com/guide/components/intents-common?hl=zh-cn)的快捷启动

❗注意：如果你的设备是Android 30（API>=30），你应该在清单中做出如下声明，否则可能会找不到对应的Activity。例如：
```xml
<queries>
    <intent>
        <action android:name="android.intent.action.DIAL"/>
    </intent>
</queries>
```

## 快速开始

```kotlin
// 拨打电话
callBtn.setOnClickListener {
    dialPhoneNumber("12345678910")
}

// 搜索给定字段
searchWeb.setOnClickListener {
    searchWeb("12345678910")
}

// 打开指定链接
openWebPage.setOnClickListener {
    openWebPage("http://www.baidu.com")
}

// 发送短信
sendMmsMessage.setOnClickListener {
    sendMmsMessage("123456","1238489")
}

// 发送邮件
sendEmail.setOnClickListener {
    openEmail(arrayOf("1550651926@qq.com"))
}

// 创建闹钟
createAlarm.setOnClickListener {
    createAlarm("你好",12,30)
}
```