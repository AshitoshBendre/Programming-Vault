```
data class User(var name: String = "", var epNo: Int = 0) {
    fun set(name: String, epNo: Int): User {
        this.name = name
        this.epNo = epNo
        return this
    }
}

fun main(args: Array<String>) {
    // Set only contains unique values; it doesn't contain duplicate values
    val list = setOf<String>("A", "B", "C", "A")
    list.forEach { println(it) }

    println()

    // Mutable Set can be edited later
    val name = mutableSetOf<String>("Ice Cream", "Waffles", "Ice Cream", "Donuts 🍩🍩")

    // Remove based on the given value && also return boolean
    val bool = name.remove("Shashikant")
    println()
    println("Does the Given String Contain the Set? \nAns: $bool")
    println()

    name.forEach { println(it) }

    // Using the corrected User class
    val user1 = User().set("Name 1", 2)
    val user2 = User().set("Name 2", 5)
    val user3 = User().set("Name 4", 9)
    val user4 = User().set("Name 4", 5)

    val users = mutableSetOf(user1, user2, user3, user4)
    println()
    users.forEach { println(it.epNo); println(it.name) }
} 

```

<H1> Output </H1>
```
A
B
C
Does the Given String Contain the Set?
Ans: false
Ice Cream
Waffles
Donuts 🍩🍩 

2 
Name 1 
5
Name 2
9
Name 4
5
Name 4
```