# Programming Paradigms & Functional Programming

In this article, we will cover the generic definition of a programming paradigm, the importance of using those paradigms, and the basic types of paradigms that other paradigms branch out from. But, we’ll be focusing more into the Functional Programming paradigm, highlighting all of its important concepts.

## What are Programming Paradigms

Programming Paradigms are procedures or techniques used to tackle problems. These paradigms are used to divide programming languages based on their strategies and implementations. Each paradigm handles different problems, such as organizing the style and syntax/grammar of a language,  grouping the code into consistent and organized units, or even managing the procedure for the execution of a program to produce a required result.

Most programming languages these days are called “Multi-Paradigm” meaning they can be used interchangeably with multiple paradigms or thought processes. An example of a really popular and paradigm-changeable used language is Python as it can be used with the Object Oriented, Procedural, or Functional paradigms.

## Why Do They Exist

Developers actually use programming paradigms as an approach to reduce the code complexity as much as possible, reducing complexity means a simpler code that can be read more easily by other developers or team members.

# Types of Programming Paradigms

Programming Paradigms can be split into Imperative, and Declarative programming paradigms, but this topic is sensitive with no main consensus. So, we’ll assume that these are the two main types, based on the paradigms we know of and will mention in the upcoming sections (again, this can be disagreed with).

## Imperative Programming

You can think of Imperative Programming as a way to guide the programming language through a set of procedures where each step is implicitly stated, such as using a For Loop on an integer array to multiply each value in that array by 2 (as shown in Example 1) instead of using a provided function to handle the transformation of the array for you.

**Example 1**

```csharp
public static int[] DoubleArray(int[] arr){
    for (int i = 0; i < arr.Length; i++){
        arr[i] = arr[i] * 2;
    }
    return arr;
}
```

## Declarative Programming

On the other side, Declarative Programming is about telling the program about what we need to be instead of telling it how to do it (using expressions and declarations), that would help in hiding the complexity to make the programming language more readable and closer to the human language (strongly-typed-ish).
**Example 2**

```csharp
public static int[] DoubleArray(int[] arr){
    Var result = arr.Select(x => x * 2 );
    return result;
}
```

# Popular Programming Paradigms

These are some of the most used Declarative and Imperative programming paradigms. We’ll be defining each paradigm as well as why it exists, we’ll be showing an example on how the paradigm works in practice, and we’ll mention the popular programming languages that are based on/use that paradigm. Keep in mind, we are not only mentioning languages that are written to support this one paradigm, rather, languages that do support the mentioned paradigm but not necessarily designed to.

Our focus will mainly be on the Functional Programming paradigm, in which we will talk in detail on how each concept in that paradigm works.

## Functional Programming

It’s a declarative programming paradigm that aims to use functions on data to reach the result needed with full separation between functions and data and without changing the data state. These are the most important topics that Functional Programming paradigms consist of (at least pure ones).

### Immutability

Functional Programming (FP) avoids changing data states or values after initializing a variable or a data structure you can’t modify it, instead, you can create a new variable or a data structure with the new data changes you need. Immutability helps in reducing data reading/accessing inconsistencies in some cases like multithreading since data values and states aren’t changing.

For example, instead of using normal loops and increasing counter variables, in FP, we replace loops with recursion.

The following example shows finding the sum from num1 to num2 with recursion: 

**Example 3** 

```csharp
public int Sum(int start , int end , int result)
{
   if(start > end )
   {
     return result ;
   }
   return Sum(start +1 , end , result + start ) ;
}
```

### Pure & Impure Functions

- **Pure Functions:** They are functions that explicitly state their outputs and inputs, and have no side effects, meaning they don’t directly modify values that are outside of the function. And their output can be summarized only by looking at the function (with no external factors).

**Example 4**

```python
def double_value(value):
    new_value = value *2
    return new_value
```

- **Impure Functions:** They are the exact opposite of Pure Functions whose outputs and inputs are hidden, thus, its output cannot be tracked solely by looking inside of the functions, but needs further context on the external values being used as inputs.

**Example 5**

```python
external_value = 10
def double_value():
    new_value = external_value *2
    return new_value

```

### First-Order & Higher-Order Functions

- **First-Class Functions:** They are functions that are called or treated as variables, these functions can be used or passed onto Higher-Order Functions.

**Example 6**

```jsx
const Calculator = {
    add:(a, b) => {
        return a + b;
    },
    subtract:(a, b) => {
        return a -b ;
    },
    multiply:(a, b) => {
        return a * b;
    },
    divide:(a, b) => {
        if (b == 0) return "Cannot divide by zero!";
        return a / b;
    }
}
```

- **Higher-Order Functions:** These are functions that either: take other functions as parameters, or return the output of other functions.

**Example 7**

```python
def create_adder(x): 
    def adder(y): 
        return x + y 

    return adder
```

### When to Use Functional Programming

- When a lot of concurrency and parallel programming is needed
- When implementing algorithms that heavily depend on mathematics
- When performing a lot of operations on the same data set

### Advantages & Disadvantages of Functional Programming

**Advantages**: 

- **High Reusability:** Since FP relies on simple components (functions) there is a higher chance for them to be a general purpose functions so this will increase the ability to reuse these functions
- **Easy To Debug & Read:** As mentioned before, since FP (pure FP) relies on pure functions which returns the same values if the same arguments were passed regardless of when they were called, it would be much easier to debug code and trace values
- I****ntrinsically Testable:****  “Isolation is an important quality of Functional Programming. An ideal function is Isolated, and that means that it's intrinsically testable.“ - [Mark Seemann](https://blog.ploeh.dk/2015/05/07/functional-design-is-intrinsically-testable/#:~:text=Isolation%20is%20an%20important%20quality%20of%20Functional%20Programming.%20An%20ideal%20function%20is%20Isolated%2C%20and%20that%20means%20that%20it%27s%20intrinsically%20testable)

 **Disadvantages**: 

- **Steep learning curve**: ****Due to FP reliability on mathematics and the fact that FP is a bit more different than other programming paradigms, make some people find it hard to learn and use. Still, it’s a relative thing and depends on that person’s pre-knowledge and preferences
- **Sometimes It gets complex due to immutability :** As seen in [Example 3](#immutability), sometimes we need to replace some simple things like loops with recursion due to violations of Immutability (since loops require modifying an iteration-variable’s value)
- **Less tools, frameworks and smaller community :** Comparing FP to other paradigms like OOP it has a much smaller community and less tools and frameworks.

### Functional Programming languages

- Haskell ( Purely Functional Language)
- F#
- Scala
- Python

### Functional Programming Examples

**Example 8**

```haskell
sub :: Double -> Double -> Double
sub x y | x == y = 0
sub x y = x - y

factorial :: Int -> Int
factorial 0 = 1
factorial x = x * factorial (x - 1)

multiplybytwo :: Int -> Int
multiplybytwo 0 = 0
multiplybytwo x = x * 2

transformlist :: [Int] -> [Int]
transformlist x = map multiplybytwo x

main = do
  let mylist = [1..10]
  putStr "Old list before map: "
  print mylist 
  let newlist = transformlist mylist
  putStr "Old list after map: "
  print mylist
  putStr "New list: "
  print newlist
```

---

**Example 9**

```python
def sub(x, y):
    if x == y:
        return 0
    return x - y

def factorial(x):
    if x == 0:
        return 1
    x = x * factorial(x - 1)
    return x

def multiply_by_two(x):
    if x == 0:
        return 0
    return x * 2

def transform_list(my_list):
    new_list = list(map(multiply_by_two, my_list))
    print('New list: ', new_list)
  
list_to_transform = [1,2,3,4,5,6,7,8,9,10]
print('Old list before map: ', list_to_transform)
transform_list(list_to_transform)
print('Old list after map: ', list_to_transform)
```

## Object-Oriented Programming

Object-Oriented Programming (OOP) is an Imperative programming paradigm that centers around objects and classes, objects being the smallest unit in the design and classes are what encapsulate those objects. This paradigm was created to make programs more modular, able to be managed and extended, and reusable, which makes the developers able to either reuse classes in the same applications or export them as “generic” components that could be used in other applications. 

### Object-Oriented Languages

- Java
- C++
- C#
- Python

**Example 10**

```csharp
public class Tax {
    private int _taxPercentage;

    public Tax(int percentage){
        _taxPercentage = percentage;
    }

    public double CalculateTaxAmount(){
        var taxAmount = _taxPercentage / 100D;
        return taxAmount;
    }
}

public class PriceCalculator{
    private Tax _tax;
    
    public PriceCalculator(Tax tax){
        _tax = tax;
    }
    
    public double CalculatePrice(double productPrice){
        var taxAmount = _tax.CalculateTaxAmount();
        var amountToSubtract = productPrice * taxAmount;
        var totalPrice = productPrice - amountToSubtract;
        
        return totalPrice;
    }
}

public class Program{
    public static void Main(string[] args) {
        var myTax = new Tax(30);
        var calculator = new PriceCalculator(myTax);
        var productPrice = 130D;
        
        var totalProductPrice = calculator.CalculatePrice(productPrice);
        
        System.Console.WriteLine(totalProductPrice);
    }
}
```

# Other Programming Paradigms

These paradigms aren’t as popular as the previously mentioned ones, but can be used to compare and differentiate between similarly designed paradigms.

## Logic Programming

Same as Functional Programming, Logic programming is a declarative programing paradigm which is mainly based on logical expressions that represents facts and rules, computations in Logic Programming use predicates which are important to create queries.

Instead of instructions, in Logic Programming, we have a collection of facts and assumptions that we inquiry using the rules to reach for the desired data, queries are widely used in Logic Programing.

### Logic Programming Languages

- Prolog
- Absys
- Alice
- ALF

## Procedural Programming

Similarly to Object-Oriented Programming, Procedural Programming is an Imperative programming paradigm which, as the name suggests, is based on procedures/functions. While Object-Oriented applications are divided into objects, Procedural ones are divided by functions.

Procedural Programming is a bit more straight-forward than Object-Oriented, because it doesn’t deal with access modifiers, inheritance, encapsulation, polymorphism, abstraction, and more Object-Oriented-specific features. But that’s what makes it less secure since not having abstraction, for example, doesn’t allow for data hiding, and not supporting inheritance, decreases code reusability, in fact, code reusability isn’t present in Procedural Programming at all.

### Procedural Programming Languages

- Fortran
- ALGOL
- COBOL
- Basic
- Pascal

## Languages Paradigm Purity

The “Pure” phrase is commonly used in Functional Programming, such as “Pure Functions”, “Purely Functional Language”, but a language being “Pure” isn’t the same throughout other paradigms. Being “Pure” in Object-Oriented Programming is a different meaning than being “Pure” in Functional Programming. Let’s compare about language purity using Object-Oriented Programming and Functional Programming.

### Purely Object-Oriented

For an Object-Oriented language to be considered pure, there needs to be seven requirements met:

1. **Abstraction**: The ability to hide irrelevant data from the users
2. **Inheritance**: The ability to inherit properties and methods from one class to another
3. **Encapsulation**: The ability to bundle a set of data (properties) along with their relevant methods
4. **Polymorphism**: The ability to change to change behavior/implementation statically (Compile-time) or dynamically (Run-time)
5. **Primitive Types are Objects**: Primitive values, such as **int**, should be treated as objects
6. **User-Defined Types are Objects**: User-defined data, i.e. Classes, should be treated as objects. e.g. User-defined classes inherit from **Object** class
7. **Methods are Bound to Objects**: All operations performed on objects must be methods bound to a certain object. e.g. **myObj.MyObjFunction()**. The use of static members violates this requirement

### Purely Functional Programming

For a functional programming language to be considered pure, there needs to be one main requirement met:

- T**he language doesn’t allow any side effects :** In order to achieve that we need the language to prevent impure functions or any expressions that have any side effect, (I/O may be an exception)

# Conclusion

In the end, there is no “ultimate” Programming Paradigm. The choice of the paradigms depends on the problem at hand. That said, some topics can be solved with multiple paradigms, especially if these paradigms belong to the same Imperative paradigm family, then it becomes the choice of choosing the better paradigm used by a certain development stack. The most commonly known and used paradigms are Object Oriented Programming, and Functional Programming.

We learned that, while using Functional programming has some great advantages like highly reusable code, better readability and easier debugging, it also has some drawbacks like higher reliance on mathematics, higher complexity due to immutability which would be more of a challenge, especially for newcomers to the programming world.

We’ve also learned about the differences between the term “Pure” from one paradigm to another. Some paradigms require more qualities to be met for it be considered pure than others, it all depends on the complexity of said paradigm.

# References

- [Introduction of Programming Paradigms - GeeksforGeeks](https://www.geeksforgeeks.org/introduction-of-programming-paradigms/)
- [What is Functional Programming? - Guru99](https://www.guru99.com/functional-programming-tutorial.html)
- [Functional design is intrinsically testable (ploeh.dk)](https://blog.ploeh.dk/2015/05/07/functional-design-is-intrinsically-testable/)
