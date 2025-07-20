# variables📦

> What are variables?

* Variables are just like containers which holds some values.
* The help to store, reuse, and update information in javascript - from simple value like numbers to complex data like array and objects and other.
* Think of a variable as a box with a name on it. You can put something inside it (a value), and later check or change what's inside in it.

* in JavaScript you can create these boxes by using `var`,`let` and `const`.

## var

* It is old way and bit risky, so if you can avoid it then suerly avoid.
* It is function-scoped(visibal onlyb inside the function where it declared).
* It can be re-declare and re-assign in the same scope.
* Hoisted to the top with undefined value.  

```
var x = 10; // declaration and initialization
console.log(`The value of x is: ${x}`)
var y = 20;

var x = 30; // re-declaration and re-initialization
console.log(`The value of x after re-declaration is: ${x}`)
var z = x + y;
console.log(`The value of z is: ${z}`)
```

## let 

* It is modern way of declearing a varible.
* It is block-scoped(visible inside only {}).headingCOntainer.
* It is re-assing but cannot be re-declare. 
* Hoisted, but stays in the Temporal Dead Zone (TDZ)

```
let age = 25;
age = 30; // ✅
let age = 40; // ❌ Error (same block)
```

## const

* It is block-scope.
* Cannot be reassigned
* Must be initialized immediately
* Good for values that don’t change (e.g. configs, references)
* TDZ applies here too

```
const pi = 3.14;
console.log(pi);

// pi = 3.14159; // ❌ TypeError: Assignment to constant variable
```

> Note

* But if const holds an object/array, you can still change its contents:

```
const person = { name: "Manish" };
person.name = "manishXcode"; // ✅ allowed
console.log(person); // { name: 'manishXcode' }
```

**Table**

|keywords|scope|redeclaration|reassignment|hosting|
|:------:|:---:|:-----------:|:----------:|:-----:|
|var|	Function	|✅ Yes	|✅ Yes	|✅ Yes (undefined)|
|let|	Block	|❌ No	|✅ Yes	|✅ Yes (TDZ)|
|const|	Block	|❌ No	|❌ No	|✅ Yes (TDZ)|

## 🔥 Scope in Real Life

* Block Scope → Code inside {} like in loops, if , etc.
* Function Scope → Code inside a function
let and const follow block scope.
* var ignores block scope — which leads to bugs.

```

{
    var x = 10;
    let y = 20;
    const z = 30;
    console.log(`Inside block: x = ${x}, y = ${y}, z = ${z}`)
}
console.log(`Outside block: x = ${x}`);
console.log(`Outside block: y = ${y}`) // ❌ ReferenceError
console.log(`Outside block: z = ${z}`) // ❌ ReferenceError
```

## 🧨 Hoisting

JavaScript prepares memory before running code.
It moves all declarations to the top — this is called hoisting.

But:

* `var` is hoisted and set to undefined
* `let` and `const` are hoisted but not initialized — so accessing them early gives
ReferenceError

## Quize(variables)

Q1. What happens here?
```
console.log(x);
var x = 10;
```

* a) Prints 10
* b) Prints undefined
* c) Throws error

✅ Answer: b) Prints undefined → due to hoisting.

Q1. What happens here?
```
console.log(x);
let x = 20;
```

* a) Prints 20
* b) Prints undefined
* c) Throws error

✅ Answer: c) Throws ReferenceError → because let variables are in TDZ.

# Data Types
