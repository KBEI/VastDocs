# RegexUtils

`RegexUtils` provides some regex checks for strings.

## Check if string is Email address

```kotlin
"12345678@qq.com".isEmail()
```

## Check if string meets password requirements

Currently this method supports three requirements:

1️⃣ Password contains at least numbers and letters.
2️⃣ Password contains two or more types:numbers,letters, and characters.
3️⃣ Password contains at least numbers and letters, and can have characters.

```kotlin
// Password contains at least numbers and letters, and can have characters.
"123456xyz.".isPwd(2)
```

Of course you can also set the length of the password:

```kotlin
// Password length between 5 and 20
"1234567.".isPwd(1,5,20)
```

## Check if string is QQ number

```kotlin
"123456710".isQQ()
```

## Check if string is a phone number

Currently only supports phone number verification in China, please refer to [2021 手机号正则表达式](https://www.jianshu.com/p/1e8eab706a63)

```kotlin
"16612341213".isPhoneNumber()
```

## Check if string is a number

```kotlin
"123456789".isNumeric()
```