
```
fun main(args: Array<String>)
{
    val list = listOf<String>("A","b","6")
    list.forEach{println(it)}
    
    
 	// Mutable List can be edited later   
	val name = mutableListOf<String>("Ashitosh", "Shashikant", "Bendre")
    
    name.add("Testing")
    
    // Remove based on the given value && also return boolean 
    val bool = name.remove("Shashikant")
    println(bool)
    
    // Removes from a specific index
    name.removeAt(0)
    
    name.forEach{println(it)}
}
```