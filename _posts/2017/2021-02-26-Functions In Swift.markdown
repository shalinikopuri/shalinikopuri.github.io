**Functions** in Swift perform various tasks just like functions in any other programming language. They can print a simple "Hello User* !" message, calculate state tax, or even perform complex operations on objects.

Functions make it easy to segregate large programs into small units of re-usable code. This code performs a small task that the entire app or the project requires regularly and the task is part of a much bigger process/requirement, which we achieve with our application on the whole.

**Definition** -

A **function** is a set of statements organized together to perform a specific task. 


Functions are a piece of code when called to perform a specific task. Functions are usually written to perform repetitive tasks in your application. Instead of using the same repetitive code else wherein the application we can simply enclose the steps in a function, name the function relevantly and call it by the name whenever necessary in the code.

- How are functions **defined/used** in Swift ?

**Function Declaration** − tells the compiler about a function's name, return type, and parameters.

**Function Definition** − it provides the actual body of the function.
The set of statements to perform the task are defined in the function definition.

**Function Parameters** and **Return Values** - function parameters and return values are extremely flexible in Swift. 
You can define anything from a simple utility function with a single unnamed parameter to a complex function with expressive parameter names and different parameter options.

*It allows us to pass local and global parameter values inside the function calls.
*

- How is a **function declared** in Swift ?

The **func** keyword tells the Swift compiler that you are declaring a function. 

Immediately following **func**, you add the **name** of the function followed by **parentheses ()**, which may or may not include a list of parameters within them. 
If the function has a **return value**, you'll write an arrow **(->)**, followed by the type of data the function will return, such as **Int**, **String**, **Person**, a **Struct** or a different **function** altogether.

Functions can be declared on their own or within a class, in which case they become a **method** that operates on objects of that class.


A simple **function definition** in Swift that says hello world to the caller.

```
func sayHelloWorld() -> String {
        return "hello, world"
  }
``` 

What are the **Types of Functions** in Swift ?

Depending on whether a function is predefined or created by a programmer, 
There are **two** types of functions in Swift:

**1. Library functions ** - Functions that are defined already in Swift Framework.

**2. User-defined functions** - Functions created by the programmer themselves.


**Library Functions**


Library functions are built-in functions that are already defined in Swift framework. These functions are present to solve common problems in Swift so that you don't have to solve them yourselves. They are simple operations like printing, finding minimum and maximum, etc.

To know more about these functions you can simply open Swift's Foundation framework, or any other framework for that matter on xcode and search for **func** keyword and browse all the functions defined in the framework.
An example is print().


**User-defined functions** - 

User defined functions are the functions written by developers and programmers. Based on the requirement the developer can define different parameters, return types and use argument labels to make the function sound more like a meaningful sentence. 

 * All these scenarios are discussed below with simple examples.*


## A typical structure of a function in SWIFT

![function-declaration.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1613939438444/nbI0-xelY.jpeg)



**Vocabulary**

**- func** is the keyword you must write to create a function.

**- functionname** - is the name of a function. You can give it any name that defines what a function does.

**- argument label** - The argument label is used when calling the function; each argument is written in the function call with its argument label before it. Functions and their arguments should be named so that they read like clear instructions when they’re called. 

**- parameter** - to be used within the function’s body, you can give a parameter two names - an argument label to be used when calling the function and a parameter name. By default, parameters use their parameter name as their argument label. But, if you explicitly define the argument name, the argument label is used when calling the function.

**- return type** - The return type is used to denote the data type or type of the value our function should return. Just like the parameter type, Xcode will enforce us to make sure that the function returns the type it specified during compile time.
-> This operator is used to indicate the return type of a function.

**- return value** -  represents the actual data being returned from the function. The value type must match the **Return Type**. The function after performing the series of steps inside the definition returns a computed value which is the return value of that function.

**return** keyword is used to transfer the control of a program to the function call and also return value from a function.
Even when you don’t specify the return keyword the function returns automatically after the execution of the last statement.

**function call** - is used to call the function with the **function name** elsewhere in the code.

**argument** - argument here is the parameter **value** required by the function to perform the task and return the result to the caller.


# How does a function work in Swift ?

![Functions Control Flow.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614299541964/AXpiqymVz.png)

In the above diagram, the statement **let value = functionName(argumentlabel: “argument”)**
invokes/calls the function with argument value **"argument"**, which then leaves the current section of code (i.e. stops executing statements below it) and begins to execute the first line of the function definition.

 - The program comes to the line of code **func functionName (argumentlabel parameter name: type ) -> return type
** and accepts the values "argument" passed during the function call "**let value  =  functionName( argument label: “argument”)
**"

  -  The program then executes the statements **statements inside the function** defined inside the function.
 
-   The statements inside the function are executed in the top to bottom order, one after the other.
   
- After the execution of the last statement, the program leaves the function and goes back to where it started from i.e **let value  =  functionName( argument label: “argument”)**.

 -   **let value =** stores the value returned from the function in a constant value. Similarly, you can store in a variable as **var value =**.
  
-  After that, statements **"statements After the function"** are executed.



Based on the images above I can simplify the permutations and combinations of types of **User - Defined** functions possible in Swift.I will try to explain each function with an example or two.

Below is a list of  **user-defined **functions I could come up in Swift with a simple explanation. I might have missed one or 2 types of functions but the examples and the long list should mostly connect the dots.

**1. Functions without Return Types or Parameters**

*Functions aren’t required to define a **return type**. *

Here’s a version of the **sayMorning()** function, which prints "Good Morning!" value rather than returning it:

Example 
```
func sayMorning( ) {
    print("Good Morning!")
}
sayMorning( )
// Prints Good Morning!

``` 
Because it doesn’t need to return a value, the function’s definition doesn’t include the return arrow **(->)** or a **return type** .The function definition still needs **parentheses ( ) **after the function’s name, even though it doesn’t take any parameters. The function name is also followed by an empty pair of parentheses when the function is called.

**Note :**
Strictly speaking, this version of the sayMorning( ) function still returns a value, even though no return value is defined. Functions without a defined return type return a special value of type **Void**. This is simply an empty **tuple**, which is written as **( )**.



**2. Functions with Return Types**

The function **sayHelloWorld( )** returns a value of type String, as the function is superseded by an arrow and the type of data the function returns using **"-> String"**.

Example
``` 
func sayHelloWorld() -> String {
        return "hello, world"
    }
    print(sayHelloWorld())
    // Prints "hello, world"

``` 


**3. Functions with Parameters**

There are times when we need to pass parameters to a function, we can pass parameters to a function like below example. We need to add a parameter msg followed by colon and the data type of msg inside the parenthesis. The data type can be some simple type like an Int or a String  and/or  can also be complex data type like structure,enum or a class or a generic.

Example
```
func greetUser(msg:String) {
    print(msg)
}
greetUser(msg: "Good Morning!")

//this function call passes "Good Morning!" String to **greetUser** function as an argument.

``` 


# 4. Function Parameters

**   - 4.1 External Parameter Names **

Let us take an example function with 2 parameters and a return type.

In the parenthesis,you can give an **argument name **followed by the **parameter name** followed by a **colon :**followed by the **type of the parameter**. Then use a **comma ,** to separate the 2nd parameter with same structure as parameter 1.

Example 
           
```
func computeSum (of firstValue: Int, and secondValue: Int) -> Int {
     return firstValue + secondValue //
}

let sum = computeSum(of: 5, and: 27)

// 

``` 
In the **function call** we just have to use the **Argument Labels** and the actual **argument/parameter value ** to call the function definition to get the return value of the sum of the passed arguments.

In this context the argument labels **"of, and"** are not actually used inside the function definition. Only the parameter names **firstValue** and **secondValue** are used in the statement 

- return firstValue + secondValue. 

That is why the argument labels **of,and** are also called **External Parameters** as they are never used inside the function definition but only during the function call to make the call more descriptive of the task at hand. 
Here, computeSum(of: 5, and: 27) - which can be read as **compute sum of 5 and 27**.



** 4.2 - Omitting External Parameter Names**

I can use the same example as above and remove the arguments labels from the parenthesis of the function. 
The compiler will not throw any error because the new function syntactically same as the old function with the argument labels.

The statement **let sumWithoutArgumentLabels = computeSum(firstValue: 5,secondValue: 21)** does not have the **argument labels** in the call but the **parameter names** used instead. 

You can try the two examples on playground and verify the same.

Example
```
func computeSum (firstValue: Int,secondValue: Int) -> Int {
     return firstValue + secondValue //
}

let sumWithoutArgumentLabels = computeSum(firstValue: 5,secondValue: 21)
print(sumWithoutArgumentLabels)
//prints 26 on the console

``` 

** 4.3 - Default Parameter Values**

Swift allows you to define functions with default parameter values. A classic example is the inbuilt **print( )** function in Swift which has 2 additional parameters which we usually tend to ignore while using it. 

func **print**(_ **items**: Any..., **separator**: String = " ", **terminator**: String = "**\n**")

**- Parameters:**

 - **items**: Zero or more items to print.
 - **separator**: A string to print between each item. The default is a single space (`" "`).
 - **terminator**: The string to print after all items have been printed. The default is a newline (`"\n"`).

Example 

```
for n in 1...5 {
       print(n, terminator: "")
    }
   // Prints "12345"

for n in 1...5 {
       print(n)
    }
//prints
//1
//2
//3
//4
//5

``` 
The terminator is simply an empty value. So the compiler prints the values without any space in the first for loop.

**4.4 - Functions With Multiple Parameters**

Functions can have multiple input parameters, which are written within the function’s parentheses, separated by commas.

**Syntax :**
       func **funcname**(**parameterName1**:Type, **parameterName2**:Type ,......) -> **(ReturnType) **         
       { 
        //statements
       }


Example

```
func volume(length: Int, width: Int, height: Int) -> String {
    print("\(length * width * height)")  //same thing you can print here 
    return "\(length * width * height)"  //return it as String
}

let result = volume(length: 5, width: 3, height: 8)
print(result) 
//"120"

``` 
This function takes a cuboid’s length, width and height as input, and returns the product of the three arguments.

**4.5 Functions with Variadic Parameters**

A **variadic function** is a function that accepts a variable number of arguments. The function arguments are represented by **… (three period characters)** after the argument’s type that can be accessed into their body as an array.

Example 1

```
// Variadic Parameters
func square(numbers: Int...) {
    for number in numbers {
        print("\(number) squared is \(number * number)")
    }
}
square(numbers: 1, 2, 3, 4, 5)
/* 1 squared is 1
 2 squared is 4
 3 squared is 9
 4 squared is 16
 5 squared is 25*/

``` 
This function calculates the square of a number range entered in the arguments, starting from 1 to 5 and printing the values on the next line on a console.

Example 2

```
func additionofnumbers(_ numbers: Int...) -> Int {
var sum: Int = 0
for num in numbers {
sum += num
}
return sum
}
print(additionofnumbers(24, 13, 37, 3, 49,51,68))

``` 
The function **additionofnumbers** takes Variadic parameters of type Int. During the function call print(additionofnumbers(24, 13, 37, 3, 49,51,68)) the values are passed as arguments to the function and then sum of the numbers **sum** is returned.


**Note: **We cannot have more than one **variadic parameter** in a function parameter.
 


 ** 4.6 - Parameter References or Functions with In-Out Parameters**

In-out parameters are passed as follows:

1. When the function is called, the value of the argument is copied.
2. In the body of the function, the copy is modified.
3. When the function returns, the copy’s value is assigned to the original argument.

This behavior is known as copy-in copy-out or call by value result. 

Example 1
```
// Functions with reference of variable as parameter value : Swapping integers.

func swapTwoInts(a: inout Int, b: inout Int) {
    let tempA = a
    a = b
    b = tempA
}
var someInt = 10
var anotherInt = 37
swapTwoInts(a: &someInt, b: &anotherInt)
print("Swapped Values : someInt = \(someInt) and anotherInt = \(anotherInt) ")

//Swapped Values : someInt = 37 and anotherInt = 10 
``` 

**Note** : **In-out** parameters can’t have **default values**, and **variadic parameters** can’t be marked as **inout**.

Example 2
```
var i = 317
print(i) //prints 317
func increment(_ i: inout Int, by x: Int) -> Int
{
    i = i + x
    return i
}
increment(&i, by: 205)
print(i) //prints 522

``` 
This function increments a value(i) by another value(x). after adding the numbers the result is returned. This function prints the new value of i. // 522

- Obviously, you can only pass a **variable** as the argument for an in-out parameter. You can’t pass a **constant** or a literal value as the argument because they cannot be modified.


** 4.7 Functions with Generics**

For creating a generic function you need to set a placeholder value after the function name in angular brackets(<>) as: *** "< Element >" ***  or *** "< T:Comparable>" ***

**Syntax:** 
         func **isAnNSObject** *** < T > ***(_ someObject: **T**) -> **Bool** { }

- You need to use the same placeholder value as parameters/return types.

- You can pass more than one placeholder value too.

- Typically, if the generic parameter placeholder doesn’t represent anything, use T, U, V etc.

- The function prototype then says that the input parameter must be of that type. That’s all there is to it for a simple generic function.

The parameterized function below can take input of any type that belongs to the Equatable protocol. We can copy the input value to a local variable and return it from the function. We can also pass the function into another function. 

Example
```
func compareAandB<T: Equatable>(a: T, b: T) {
print
(
"a == b ? \(a==b)"
) } 

compareAandB(a: 2, b: 3) 
//a == b ? false

compareAandB(a:"Hi", b:"Hi")
//a == b ? true

```
The generic **T** conforms to **Equatable** protocol in this example. Any variable/constant of the type that conforms to this protocol can be used as arguments to **compareAandB** function. 
**Int** and **String** conforms to Equatable protocol, so this example does work and returns a **Bool** value.

By defining a generic parameter we made this simple function re-usable with multiple data types which conform to  Equatable protocol.

**5. Functions as Types**

What exactly is a function’s **"Type"** or a **“Signature”** ?

Two things:

1. The Type(s) of its **parameters**.

2. The **Return Type** that the function returns.

Combining the Type(s) that the function receives as inputs, and the Type that it returns composes to give the function its **"Type" / “Signature”**.

Every function in Swift has a type, consisting of the function’s parameter types and return type. You can use this type like any other type in Swift, which makes it easy to pass **functions as parameters to other functions**  and to **return functions from functions.** 
Functions can also be written within other functions to encapsulate useful functionality within a nested function scope.

Example 1
```
func generateAncientWarName(fname: String, lname: String, byear: Int) -> String 
{ 
   // ... 
}
``` 

“What is the **generateAncientWarName** function’s Type?”

The answer is “generateAncientWarName is a function of Type that has three parameters, the first two of type String, the last of type Int, and that returns a value of type String.”

The Function Type is a mouthful, but it does explain in precise terms what the function’s **Type** is.

Essentially, it boils down to stripping away the **function’s name** and the **parameter names** to leave behind the raw **Type** information that composes to give the function its **Type**.

Given the above generateAncientWarName function, we could notate its Type as follows:

**(String, String, Int) -> String**

## Function types and their Uses:

if a function,    
      
- Takes an **int** and returns an **int** then the function's
**TYPE is : Int -> Int**
                    
- Takes an **int** and a **string**, returns **nothing** then the function's 
**TYPE: (Int, String) -> ()**
                  
- Has **No parameters**, returns **two doubles** then the function's **TYPE: () -> (Double, Double)**

    
```
func printHello() {
        print("hello, world")
    }
``` 

- The function **Type** of this simple function can be read out as **“a function that has no parameters, and returns Void/nothing.”**


Note - **Functions** are first class objects and also reference types like a **Class** or a **Closure** in Swift.

### Uses of Function TYPES.

**5.1. Function Types as Parameter Types**

Syntax :
    func **map**(_ array: **[Int]**, _ transform: **(Int) -> Int**) ->** [Int]** { }

 - the map function here is taking an array of Int and a "function with Int as a single parameter, return type as an Int " and returns an array of Int.

- func map TYPE : a function that has 2 parameters, one Array of Int and second a function of type "a parameter of Int and returns an Int", returns an Array of Int.

Example
```
//Function as TYPE and a function type as a parameter of a function.

func map(_ array: [Int], _ transform: (Int) -> Int) -> [Int] {
    var result = [Int]()
    for element in array {
        result.append(transform(element))
    }
    return result
}

// map can be used with other functions
// and also closures which are functions
// without a name and can be created "on the fly"
func addByOne(i: Int) -> Int {
    //the function addByOne's Type : a funcion with an Int as a parameter and returns a value of Int.
    return i + 1
}
func square(i: Int) -> Int {
    //the function square's Type : a funcion with an Int as a parameter and returns a value of Int.
    return i * i
}
map([3,2,5], addByOne) // [4,3,6]
map([4,7,11], square) // [16,49,121]

``` 

**5.2. Function Types as Return Types**


**Syntax - **
              func **chooseANewStepFunction**(backward: Bool) -> **(Int) -> Int **{ }

The function **chooseANewStepFunction** takes a Bool as a parameter and a function as return type, the function itself has a TYPE which reads as **" a function with one parameter as an Int, returns an Int "**

Example 1
```
/*
  Function Type as a Return Type for a function
 */
func chooseANewStepFunction(backward: Bool) -> (Int) -> Int {
    func goForward(input: Int) -> Int { return input + 1 }
    func goBackward(input: Int) -> Int { return input - 1 }
    return backward ? goBackward : goForward
}
currentValue = -4
moveNearerToZero = chooseANewStepFunction(backward: currentValue > 0)
// moveNearerToZero now refers to the nested chooseANewStepForward() function
while currentValue != 0 {
    print("\(currentValue)... ")
    currentValue = moveNearerToZero(currentValue)
}
print("zero!")

``` 
The beauty of coding functions is that you can get your output in multiple ways. You can alter the steps inside the function and achieve the same result. Below is an example to demonstrate the same.

Example 1 : **Alternate Code**

```
func chooseANewStepFunction(backward: Bool) -> (Int) -> Int{
    backward ?{$0 - 1}:{$0 + 1}
}
var currentValue = -5
var moveCloserToZero = chooseANewStepFunction(backward: currentValue > 0)
while currentValue < 1 {
    print("\(currentValue)... ")
        currentValue = moveCloserToZero(currentValue)
    }
    print("zero!")

//prints
//-5... 
//-4... 
//-3... 
//-2... 
//-1... 
//0... 
//zero!


``` 
This code simply eliminates 2 nested functions inside the function **chooseANewStepFunction** which are redundant in this case. Using closures is one way to write series of steps in swift. All you have to do is enclose the statements in **{ }**. 
Closures is a big topic altogether, so I will refrain from getting into it.


Example 2

**makeLogger** function below has a return type as a Function with Type as "a String as a parameter and returns a String".

func **makeLogger**() -> **(String) -> String **{ }

```
//A function Type as a return Type for another function.

func makeLogger() -> (String) -> String { 
// makeLogger function has a return type as a Function with Type as **"a String as a parameter and returns a String"**

    func log(s:String) -> String {
        // log function here has a Type : "a String as a parameter and returns a String" 
        print(s)
        return(s)
    }
    return(log)
}

let myCustomLog = makeLogger()
myCustomLog("I am a log message")

``` 

**6. Functions with Multiple Return Values**


You can use a **tuple type** as the return type for a function to return multiple values as part of one compound return value.

The example below defines a function called minMax(array:), which finds the smallest and largest numbers in an array of Int values:

Example 1
```
// Functions With Multiple Return Values
func minMax(array: [Int]) -> (min: Int, max: Int) { 
//takes an Array of Int data type as the parameter values.
    var currentMin = array[0]
    var currentMax = array[0]
    for value in array[1..<array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax) // returns a tuple
}

let bounds = minMax(array: [18, -8, 2, 49, 31, 79)
print("min is \(bounds.min) and max is \(bounds.max)")
// Prints "min is -8 and max is 79"

``` 

**Example 2**
```
func findTopThree(array : [Int]) ->(first : Int, second : Int, third : Int){
    var currentFirst = -1
    var currentSecond = -1
    var currentThird = -1
    
    for value in 0...array.count-1 {
        if (array[value] >= currentFirst){
            currentThird = currentSecond
            currentSecond = currentFirst
            currentFirst = array[value]
        }else if (array[value] > currentSecond){
            currentThird = currentSecond
            currentSecond = array[value]
        }else if(array[value] > currentThird){
            currentThird = array[value]
        }
    }
    
    return (currentFirst,currentSecond,currentThird)
}

let marks = [35, 46, 34, 29, 59, 70, 82, 89, 45,80,95, 87,23, 49,91]

let result = findTopThree(array:marks)
print ("Topper : \(result.first)")
print ("Second Highest : \(result.second)")
print ("Third Highest : \(result.third)")


// Prints below output on console.
// Topper : 95
//Second Highest : 91
//Third Highest : 89

``` 

In this example, we are finding out the top three marks from an array of marks. The return value of the function is defined as **->(first : Int, second : Int, third : Int)** i.e. it will return three integers in a **tuple** with name **’first’, ’second’ and ’third’.** 
We created one constant **’result’** to hold these values. Since, the values of a tuple are named the same as the return type defined in the function, we can access each one of them using a** dot ’.’** . The last three print lines are used to print out the ’first’, ’second’, and ’third’ values of that tuple. 


Example 3 with **optional** Multiple Return Values


```
func findFirstTwoNegativeNumbers(array : [Int]) -> (first : Int, second : Int)? {
    var firstNumber = 0
    var secondNumber = 0
    
    for value in 0...array.count - 1 {
        if(array[value] < 0){
            if firstNumber == 0 {
                firstNumber = array[value]
            }else if secondNumber == 0{
                secondNumber = array[value]
                return (firstNumber,secondNumber)
            }
        }
    }
    return nil
}

let numbers = [ 5,31,9,2,16]
print("First two -ve numbers are \(findFirstTwoNegativeNumbers(array : numbers))")

let numbers2 = [ 17,21,35,-13,4,5,-47,0,9,-5]
print("First two -ve numbers are \(findFirstTwoNegativeNumbers(array : numbers2))")

//Prints 
//First two -ve numbers are nil
//First two -ve numbers are Optional((first: -13, second: -47))

``` 
The function is used to find out the first two negative numbers in an array. Here , the return type is **(first : Int, second : Int)? ** i.e. it may or may not return results or the return type values can be **optional**. If it will find two negative numbers in the input array, it will return these as a tuple. If one or no negative numbers are found in the array, it will return **nil**. 
For the first example, since all the numbers are positive, it returns ‘nil’. 



**7. Nested Functions**

A single function or multiple functions defined inside of a parent/master function is called a Nested Function.

- Nested functions must be defined before the body of their master function.

Example 1

```
// Nested functions 

func operate(with symbol:String) -> (Int, Int) -> Int {
    func multiply(num1:Int, num2:Int) -> Int {
        return num1 * num2
    }
    func divide(num1:Int, num2:Int) -> Int {
        return num1 / num2
    }
    let operation = (symbol == "multiply") ?  multiply : divide
    return operation
}
let operation = operate(with: "multiply")
let resultOp = operation(25, 10)
print(resultOp)

// prints 250 after multiplying.

``` 
In the above code,the master function is **operate()**, with return value of type Function **(Int,Int) -> Int**.
The **inner (nested)** functions are **multiply() **and **divide().**

The nested function multiply() and divide() in a way are being used outside of the enclosing function operate(). This is possible because the master function returns one of these functions.

Example 2

```
func summer(_ numb: Double) -> (Double...) -> Double {
    // Closure: the nested function is able to close over `num`.
    var numb = numb
    func internalFunc (numbers: Double...) -> Double {
        for i in numbers {
            numb = numb + i
        }
        return numb
    }

    return internalFunc
}

var sum = summer(34.0)(52.0, 13.0)
print(sum)
// 99.0\n

``` 



**8 . Recursive Functions**

A function calling itself is called a recursive function.

- This procedure is called **Recursion**

Example 
```
//Recursive function calculates factorial of a number N.

func factorial(of num: Int) -> Int {
    if num == 1 {
        return 1
    } else {
     return num * factorial(of:num - 1)
    }
}

let x = 10
let result = factorial(of: x)
print("The factorial of \(x) is \(result)")

``` 

The factorial function is called itself until the value of x is reduced to a value of 1 and the result constant saves the calculated factorial value of x.


**9. Mutating Functions**

**Structures** and **enumerations** are value types in Swift.A  **value type** is the one that creates a copy of its object and passes only the copy when passed as a parameter.
By default, the properties of a value type cannot be modified from within its instance methods.

The compiler will throw an error saying  ***cannot assign to property: 'self' is immutable***

Xcode compiler will also suggest a FIX saying  ***Mark method 'mutating' to make 'self' mutable***

However, if you need to modify the properties of your structure or enumeration within a particular method, you can opt into mutating behavior for that method. The method can then mutate (that is, change) its properties from within the method, and any changes that it makes are written back to the original structure when the method ends. 

Example
```
struct Town
{
  var population : Int 
//error: cannot modify property "population" without adding mutating keyword
  mutating func changePopulation(newpopulation : Int) {
     population = newpopulation 
  }
}
  var mytown = Town(population : 500)
  mycity.changePopulation(newpopulation : 2000)

``` 

**10. Higher order functions in Swift**

Higher order functions in Swift are extremely powerful tools to have a touch with, the only issue is that it might take some time to get comfortable with them. 

**Examples **- map, reduce and sorted, etc

Before we get started, let’s have a look at some important terms to know in relation to higher order functions :

**Collections** - a sequence or collection of elements that can be traversed multiple times, non-destructively.

Eg - Arrays,Sets and Dictionaries.

**Closures** - self-contained blocks of functionality that can be passed around and used in the code.

**Shorthand arguments **- Swift automatically provides shorthand argument names to inline closures, which can be used to refer to the values of the closure’s arguments by the names $0, $1, $2, and so on.

**Optional** - A type that represents either a wrapped value or nil, the absence of a value.

Example 1

**Filter** - Filter is used when you want to have a result with only elements that match a specific condition.
```

//Example 1 - Filter only the planets that start with the letter **"M"**

let planetNames = ["mercury", "venus", "earth", "mars", "jupiter", "saturn", "uranus", "neptune", "pluto"]

let filteredPlanetNames = planetNames.filter {$0.prefix(1).uppercased() == "M"}
print("Count of filtered planet names: \(filteredPlanetNames.count)")

//prints Count of filtered planet names: 2

``` 

Example 2 - Filter the address array to only addresses from zipcode 31820

```
var addresses = [Address]()
addresses.append(Address(street: "Veterans Pkwy", zipcode: 31820))
addresses.append(Address(street: "Manchester Street", zipcode: 31839))
addresses.append(Address(street: "Kitten Lake", zipcode: 31820))

// Example 2: Filter the address array to only addresses from zipcode 31820

let filteredAddresses = addresses.filter {$0.zipcode == 31820}
for n in 0...filteredAddresses.count - 1 {
    print("Filtered address Street: \(filteredAddresses[n].street)")
}


``` 

# Function Overloading in Swift

What is function overloading?

By definition, the process of defining **two** or **more than two functions** with the **same name** but varies by the difference in  **number** or **types** of **parameters** or data type of **Return Type **passed by the function is known as function overloading.

Example 1
```
func sameName() {
  ...
}
func sameName(parameter: Int) {
  ...
}
``` 

Example 2

``` 
// function overloading

func greetABaby(person: String) -> String {
    let greeting = "Hello, " + person + "!"
    return greeting
}

print(greetABaby(person: "Aayush"))
// Prints Hello Aayush

func greetAgain(person: String) -> String {
    return "Hello again, " + person + "!"
}
print(greetAgain(person: "Aayush"))
// returns Hello again, Aayush

// Functions With Multiple Parameters
func greetABaby(person: String, alreadyGreeted: Bool) -> String {
    if alreadyGreeted {
        return greetAgain(person: person)
    } else {
        return greetABaby(person: person)
    }
}
print(greetABaby(person: "Aayush", alreadyGreeted: true))

// Prints "Hello again, Aayush!"


``` 
You call the **greetABaby**(person:,alreadyGreeted:) function by passing it both a **String** argument value labeled **person** and a **Bool** argument value labeled **alreadyGreeted** in parentheses, separated by commas. 
Although both functions have names that begin with greetABaby, the **greetABaby(person:alreadyGreeted:)** function takes two arguments but the **greetABaby(person:)** function takes only one. 
This phenomenon is called function overloading.

***Note*** : All of the above discussed user-defined function combinations are possible with Overloading in Swift. I am not going to discuss those examples as they can get cumbersome and repetitive.





# Function Overriding in Swift

Function Overriding enables a **sub-class** or a **child class** to override the variables or functions/methods from its **parent class**.

Simply put, your child class can access/use all the member types of the class it conforms to(Parent Class) and this is called **Inheritance**.

You need to specify **override** keyword before the function definition to let the compiler know that the sub-class is going to override that function and implement it's own logic when called by an object.

Example
``` 
class SalesCalculator {
    var salesPrice = 20
    
    func income(sellingPrice: Double) -> Double {
        return sellingPrice
    }
    
    func getSalesPrice() -> Int {
        return salesPrice
    }
}
class TaxCalculator: SalesCalculator {
    override func income(sellingPrice: Double) -> Double {
        return sellingPrice * 0.8
    }
}

``` 

The Class **SalesCalculator** is the **Parent Class** and the class **TaxCalculator** conforms to **SalesCalculator** class which means TaxCalculator is the **sub-class** of  **SalesCalculator** and all the properties and functions of the Parent Class can be accessed by the child class.


***Note*** : All of the above discussed user-defined function combinations are possible with Overriding in Swift. I am not going to discuss those examples as it can get tiring and repetitive.


To recap, in this blog post, we learned all about functions. We saw how to give functions parameters as well as return types. We also saw how to name external parameters and the various modifications we can add to the parameters to allow us to make it more readable like adding argument labels. Finally, we learned how to use functions like variables, both as parameters and return types to other functions. I also explained about mutating methods/functions, recursive functions, nested functions, and higher order functions in swift. I tried to emphasize the many possibilities of mixing up different kinds of User-Defined functions with examples in swift. I had to explain the basics of Function overloading and overriding. 
To finish off I am going to mention the **advantages** of using functions and **things to remember** while writing functions in swift or any other programming language for that matter.


# Advantages of using Functions


- It implements re-usability.
- Collaboration and development can be shared and made easy.
- Reduces coupling
- Reduces redundancy and duplication.
- It enhances the modularity of the project or application.



# Things to remember while writing User-Defined functions.


1. Give a function name that reflects the purpose of the function.

2. Try to make your function reusable, think ahead, and group the statements needed.

3. The **"more the merrier"** phrase all of a sudden sounds exhaustive right? Yes at first. 
But with little practice, you can get hold of all the variations and syntax. In fact functions are a powerful way to process and manipulate your data objects according to the requirements. Hence all these variants will only help us in developing reusable code.

4. A function should accomplish only one task. If you want to get multiple things done
try to break down each task into a distinct function, with a unique name that defines the task.

5. Try to browse a few methods/functions that are available in swift **LIBRARIES** like **Foundation Framework** etc.



***P.S :- ***  **I started this post to understand functions and the syntax of functions in Swift. 
But once I dug deep, I understood that it is going to be a long journey until I can master functions in Swift, needless to say, totally worth it. All the variations of functions above can/will be used in the future while developing an App.
All the examples here are collected from various other posts and works well in the playground. So feel free to try them. 

*PRACTICE IS THE ONLY WAY TO GET HOLD OF ANY TECHNOLOGY.* **
************
