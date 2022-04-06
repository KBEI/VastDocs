# IDCardUtils

`IDCardUtils` is used to verify the correctness of the Chinese resident ID card number locally. The usage method is as follows:

```kotlin
IDCardValidate("123456789101112131")
```

Here are possible error：

1️⃣ The length of the ID number is not 15 or 18 digits.
2️⃣ The 15-digit ID number is not all digits; the 18-digit number is not all digits except the last digit.
3️⃣ The birthday of the ID card is invalid.
4️⃣ The birthday of the ID card is not valid.
5️⃣ The month of the ID card is invalid.
6️⃣ The date of the ID card is invalid.
7️⃣ The ID card area code is wrong.