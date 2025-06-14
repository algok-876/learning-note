### 遍历列表
#### for .. in循环
#### forEach函数
```kotlin
fun main() {  
    val list = listOf("123", "456", "567")  
    for(item in list) {  
        println(item)  
    }  
  
    list.forEach { item ->  
        println(item)  
    }  
}
```

#### forEachIndexed
在lambda表达式中可以获取索引
```kotlin
list.forEachIndexed {index, item ->  
    println("index: $index, item: $item")  
}
```

### 解构
```kotlin
val (item1, item2) = list
```