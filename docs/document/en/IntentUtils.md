# IntentUtils

`IntentUtils` provides you some common [Intent](https://developer.android.com/guide/components/intents-common)

Note: If your device is Android 11 (API>=30), you should make the following declaration in **AndroidManifest.xml**, otherwise the corresponding Activity may not be found. E.g:

```xml
<queries>
    <intent>
        <action android:name="android.intent.action.DIAL"/>
    </intent>
</queries>
```

## Quick Start

### Initiate a phone call

```kotlin
callBtn.setOnClickListener {
    dialPhoneNumber("12345678910")
}
```

### Perform a web search

```kotlin
searchWeb.setOnClickListener {
    searchWeb("12345678910")
}
```

### Load a web URL

```kotlin
openWebPage.setOnClickListener {
    openWebPage("http://www.baidu.com")
}
```

### Compose an SMS/MMS message with attachment

```kotlin
sendMmsMessage.setOnClickListener {
    sendMmsMessage("123456","1238489")
}
```

### Compose an email with optional attachments

```kotlin
sendEmail.setOnClickListener {
    openEmail(arrayOf("12345678@qq.com"))
}
```

### Create an alarm

```kotlin
createAlarm.setOnClickListener {
    createAlarm("Hello",12,30)
}
```

### Open wifi settings

```kotlin
wifiSetting.setOnClickListener {
    openWirelessSettings()
}
```