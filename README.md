
# Kotlin Cheat Sheet

Kotlin Language Cheat Sheet


```
###############################################
############### Hello, Kotlin! ################
###############################################
~~~~~~ kerimbr.com | github.com/kerimbr ~~~~~~~
###############################################
````


## Variables

#### Code

```
    var var1 = 10;

    var name: String = "Kerim"
    var surname: String = "Bora"
    var age: Int = 23
    var height: Double = 1.86
    var phoneNumber: Long = 5453720000
    var isMarried: Boolean = false

    

    // constant
    val pi: Double = 3.14

    println(
        "Name: ${name} \n" +
        "Surname: $surname \n" +
        "Age: $age \n" +
        "Height: $height \n" +
        "Phone Number: $phoneNumber \n" +
        "Is Married: $isMarried \n"
        );


    // Conversion

    var myNumber = 5;
    var myLongNumber = myNumber.toLong();
    println("My Long Number: $myLongNumber")

    var input = "10";
    var myInt = input.toInt();
    println("My Int: $myInt")
```

#### Output

```
Name: Kerim 
Surname: Bora 
Age: 23 
Height: 1.86 
Phone Number: 5453720000 
Is Married: false 

My Long Number: 5
My Int: 10
```


## Collections

#### Code

```
    // Array
    val myArray = arrayOf(1,2,3,4,5,6,7,8,9,10)
    println("Array: ${myArray[2]}")

    // List

    var myArrayList = arrayListOf(1,2,3,4,5,6,7,8,9,10)
    myArrayList.add(11)
    println("List: ${myArrayList[2]}")

    val myGenericList = listOf<String>("Kerim", "Bora")
    println("Generic List: ${myGenericList[1]}")

    val myDoubleList = ArrayList<Double>()
    myDoubleList.add(1.2)
    myDoubleList.add(1.3)
    myDoubleList.add(1.4)
    println("Double List: ${myDoubleList[2]}")

    val myDynamicList = ArrayList<Any>()
    myDynamicList.add(1)
    myDynamicList.add("Kerim")
    myDynamicList.add(1.2)
    println("Dynamic List: ${myDynamicList[2]}")


    // Set

    val mySet = setOf<Int>(1,1,2,2,3,3,4,4,5,5)
    println("Set Size: ${mySet.size}")
    

    // Lambda Expression: {}
    // it(item): element(value-parameter) 
    mySet.forEach {
        println(it)
    }


    // Map (Dictionary)

    val fruitCalories = hashMapOf<String,Int>()
    fruitCalories.put("Apple", 100)
    fruitCalories.put("Orange", 200)
    fruitCalories.put("Banana", 300)
    println("Orange Calories: ${fruitCalories["Orange"]}")

    val myHashMap = HashMap<String,Int>()
    val myNewMap = hashMapOf<String,Int>("Apple" to 100, "Orange" to 200, "Banana" to 300)
```

#### Output

```
Array: 3
List: 3
Generic List: Bora
Double List: 1.4
Dynamic List: 1.2
Set Size: 5
1
2
3
4
5
Orange Calories: 200
```
## Operators

#### Code

```
    // Comparison Operators 
    // ==, !=, >, <, >=, <=

    // Logical Operators
    // &&, ||, !

    // Bitwise Operators
    // &, |, ^, <<, >>

    // Assignment Operators
    // =, +=, -=, *=, /=, %=

    // Special Operators
    // in, !in, is, !is

    // Range Operators
    // .., until

    // Null Safety
    // ?.

```

## Control Flow

#### Code

```
    // if-else

    var age = 23;

    if(age < 18){
        println("You are not adult")
    } else if(age == 18){
        println("You are adult")
    } else {
        println("You are adult")
    }


    // when (switch-case)

    when(age){
        0,1,2 -> println("Baby")
        in 3..6 -> println("Kid")
        7,8,9,10 -> println("Pre-Teen")
        11,12,13,14,15,16 -> println("Teen")
        17,18 -> println("Young Adult")
        23 -> println("You are 23")
        else -> println("Adult")
    }
```

#### Output

```
You are adult
You are 23
```
## Loops

#### Code

```
    // for

    val myArray = arrayOf("Kerim", "Bora", "Kotlin", "Android")

    for(item in myArray){
        println(item)
    }

    // indices: index
    for(index in myArray.indices){
        println("index: $index, value: ${myArray[index]}")
    }

    println("b loop: ");
    for(b in 1..10){
        println(b)
    }

    println("c loop: ");
    for(c in 10 downTo 1){
        println(c)
    }

    println("d loop: ");
    for(d in 1..10 step 2){
        println(d)
    }

    println("e loop: ");
    for(e in 10 downTo 1 step 2){
        println(e)
    }

    println("f loop: ");
    for(f in 1 until 10){
        println(f)
    }

    println("----------------")

    // while
    println("while loop: ");
    var i = 0;
    while(i < 10){
        println(i)
        i++;
    }

    // do-while
    var j = 0;
    do{
        println(j)
        j++;
    } while(j < 10)


    // for each

    val myArrayList = arrayListOf("Kerim", "Bora", "Kotlin", "Android")
    myArrayList.forEach {
        println(it)
    }
```

#### Output

```
Kerim
Bora
Kotlin
Android
index: 0, value: Kerim
index: 1, value: Bora
index: 2, value: Kotlin
index: 3, value: Android
b loop: 
1
2
3
4
5
6
7
8
9
10
c loop: 
10
9
8
7
6
5
4
3
2
1
d loop: 
1
3
5
7
9
e loop: 
10
8
6
4
2
f loop: 
1
2
3
4
5
6
7
8
9
----------------
while loop: 
0
1
2
3
4
5
6
7
8
9
0
1
2
3
4
5
6
7
8
9
Kerim
Bora
Kotlin
Android
```
## Functions

#### Code

```

    // Void(Unit) Function
    fun myVoidFunction(){
        println("My Void Function")
    }

    myVoidFunction()

    // Return Function

    fun sum(a: Int, b: Int): Int{
        return a + b;
    }
    println("Sum: ${sum(2,3)}")

    fun sum2(a: Int, b: Int) = a + b;
    println("Sum2: ${sum2(2,3)}")

    /*
        fun [functionName]([parameterName]: [parameterType]): [returnType]{
            return [value]
        }
    */
```

#### Output

```
My Void Function
Sum: 5
Sum2: 5
```
## Classes

#### Code

```


class Simpson{

    // Properties
    var name = ""
    var age = 0
    var job = ""

    private var isMarried = false

    constructor(name: String, age: Int, job: String){
        this.age = age;
        this.name = name;
        this.job = job;
    }

}


    var homer = Simpson("Homer", 40, "Nuclear Safety");

    homer.name = "Homer";
    homer.age = 40;
    homer.job = "Nuclear Safety Inspector";


    // Nullability (?) -> Nullable (!!) -> Non-Nullable 

    var homer2: Simpson? = Simpson("Homer", 40, "Nuclear Safety");

    var nullableData: String? = null;
    println("nullableData: $nullableData")

    // Non-Null Assertion Operator (!!)
        // println(nullableData!!) 
        // NullPointerException (not-initialized)

    // Null Safety

    if(nullableData != null){
        println(nullableData)
    }else{
        println("nullableData is null")
    }

    // Safe Call (?.)
    println(nullableData?.length)
    
    // Elvis Operator (?:)
    println(nullableData?.length ?: 0)

```

#### Output

```
nullableData: null
nullableData is null
null
0
```
