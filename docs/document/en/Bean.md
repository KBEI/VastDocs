# Bean

## User

```kotlin
open class User(val username: String, val password:String)
```

## Response

```kotlin
open class Response<T:Any> (val code:Int,val msg:String,val data:T)
```