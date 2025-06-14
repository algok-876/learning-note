kotlin中默认都是非可空变量，定义可空变量需要在变量末尾加上？
```kotlin
var a:Int? = 123  
a = null
```
kotlin不允许在可空类型的变量上调用函数，因为这是类型不安全的。如果必须需要在可能为空的类型变量上调用函数，可以通过以下三种方式来确保类型安全

### 安全调用
可以使用安全调用符`?.`，来调用函数，如果调用者为空则跳过函数执行，不会产生空指针异常
```kotlin
val line = readlnOrNull()  
val upperLine = line?.replaceFirstChar { if (it.isLowerCase()) it.titlecase(Locale.getDefault()) else it.toString() }  
println(upperLine)
```

### 非空断言操作符
!!.操作符也能用来在可空类型上调用函数，但这是很危险的，它表示，你能够确保该变量一定不为空，为空则会抛出空指针异常
```kotlin
val line = readlnOrNull()  
val upperLine = line!!.replaceFirstChar { if (it.isLowerCase()) it.titlecase(Locale.getDefault()) else it.toString() }  
println(upperLine)
```
如果在控制台什么也不输入，则会抛出异常

### 空值合并符
空合并操作符`?:`，它的意思是如果左边求值的结果是null，则使用右边的表达式结果
```kotlin
val line = readlnOrNull()  
val upperLine = line?.replaceFirstChar { if (it.isLowerCase()) it.titlecase(Locale.getDefault()) else it.toString() }  
    ?: "default value"  
println(upperLine)
```

