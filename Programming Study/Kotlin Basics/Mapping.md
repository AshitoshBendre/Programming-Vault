
Mapping refers to transforming or converting elements of a collections (like a list, set, or array) into another collection of the same or different type. this is done using the map function, which applies a given transformation function to each element in the collection and returns a new collection containing the transformed elements

<h2>Syntax</h2>

```Kotlin fold:"Syntax"
val transformedCollection = originalCollection.map{ element -> transformation }
```

<h2>Examples</h2>

```Kotlin fold:"Transforming to Squares"
val numbers = listOf(1,2,3,4)
val squares = numbers.map {it * it}
println(squares) // Output: [1,4,5,16]
```

```Kotlin fold:"Mapping to a Different Type"
val words = listOf("Kotlin", "Mapping", "Example")
val lengths = words.map{ it.length }
println(lenghts) // Output : 6, 7, 7 
```


``` Kotlin fold:"Using Custom Transformation Function"

	fun capitalize(word: String): String = word.uppercase()

	val words = listOf("kotlin","is","fun")
	val capitalizedWords = words.map(::capitalize)
	println(capitalizedWords) // Output: [KOTLIN, IS, FUN]
```

> Here the `::` at line 6 before capitalize is used to create a function reference to the capitalize function. It tells the `map` function "For each element in the collection, call the `capitalize` function"

```Kotlin fold:"Chaining Mapping Operations"
	val numbers = listOf(1, 2, 3, 4, 5)
	val result = numbers.filter { it % 2 == 0 }.map { it * 2 }
	println(result) // Output: [4, 8]

```

<h2>Advance Mapping Functions</h2>

```Kotlin fold:"mapIndexed"
	val numbers = listOf(10,20,30)
	val result = numbers.mapIndexed { index, value -> "$index: $value"}
	println(result) // Output: [0: 10, 1: 20, 2: 30]

```

```Kotlin fold:"map not null check"
 val numbers = listOf(1,2,3,null,5)
 val doubled = numbers.mapNotNull { it?.times(2) }
 println(doubled) // Output: [2, 4, 6, 10]
```

```Kotlin fold:"Maps and flattens nested collections"
	val lists = listOf(listOf(1, 2), listOf(3, 4))
	val flatResult = lists.flatMap { it.map { number -> number * 2 } }
	println(flatResult) // Output: [2, 4, 6, 8]
```

