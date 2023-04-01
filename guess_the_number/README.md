## This is a practice program that reproduces a guessing game. 


 This is a practice program that reproduces a guessing game. 
 The user is promped with a choice to pick a number in between 1-100. Once the user inputs the choice, the program will indicate if the guess is correct or not.

### Concepts introduced in this practice session
- let 
- match  
- methods
- standard library
- preludes


**std::io**
std is the standard library in Rust.
**io** is the input/output library included in the standard set of items called *preludes*



**Variables are immutable by default**

This is the standard case in rust, so something like `let apple = 5 // immutable` will always have  the value of 5.
The very obvious workaround in this language is prefixing the variable with the keyword **mut** that stands for *mutable*
`let mut apple = 5 // mutable` 

**Associated functions**

These are functions that are implemented on a type, like String.
We bring this up now  because of this example in the program: `let mut guess = Sring::new()` that creates a mutable variable that is now bound to 
and empty instance of type String.

It kind of make sense if you look at this code `io::stdin()` which is the function we call to receive the input from the user.
To read that in human language would be something like: import the `io //input/output` then call the `stdin()`function from that library.

**.read_line(&mut guess)**

Chaining a method, that's clear, the sort of odd bit here is the `mut` which makes sense, given what we know, because it's basically telling the method that 
string passed as argument can be updated.

**References**

The `&` sign means that the variable is a reference: `(&mut guess)` in fact, it was declared before the method. This is a complex feature, but it's incredible to see it in action.
It's basically telling the program to go an fish out of memory the reference address of the variable we have previously declared, thus avoiding us to have to store that same variable in memory multiple times.
Like variables, **references are also immutable by default**.

**read_line - enums and variants**

Things are starting to get interesting. the `.read_line` puts whatever the user types into a string **but it also returns a Result value**
**Result is an enumeration or enum** which is a **type that can be in one of multiple states.** Each of these possible states are called **variants**

Result's variants are **OK** and **Err** The `Err` variant tells us if the operation has failed and carries information as to why it has failed.
The `OK` value tells us that the operation succeeded and contains the successfully generated value.
**Values of any type have methods defined on them** and so `Result` has a method `expect()` that you can call. If the instance of `Result` is an `Err` then 
the program will crash and display the message you passed as argument of `expect()`
If the instance of `Err` is `OK` the `expect()` method will return the succesful value so you can use it.

**Placeholders {}**

These are amazing. They look like template literals in JavaScript, and in a way they work the same.
For example:

```
let x = 5;
pintln!("The value of X is {x}")
```
However, you can also use them to evaluate the result of an expression! (wow)

```
let x = 5;
let y = 10;

pintln!("X is equal to {x} and y + 2 = {}", y + 2);
```
The code will print: `x = 5 and y = 12`















## References
[Preludes](https://doc.rust-lang.org/reference/names/preludes.html)
