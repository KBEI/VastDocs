# Bean

## User

定义如下

```kotlin
open class User(val username: String, val password:String)
```

## Response

定义如下

```kotlin
open class Response<T:Any> (val code:Int,val msg:String,val data:T)
```