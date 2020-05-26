# Deep Javascript Foundations v3
## Kyle Simpson
# Types - Section 1

### FALSE: In javascript everything is an object

### Instead, javascript is made up of primitive types
- a lot of things can *behave* like objects in JS, but to say the above statement, as is often claimed is not correct

## JS **primitive types** are:
    - undefined
    - null
    - boolean
    - string
    - symbol 
    - number 
    - object
    - symbol
    
### *What about the following?*
- undeclared
- null *this is a type but it behaves strangely*
- function
- array
- bigInt?

### In JavaScript, variables do not have types, values do.

### **TypeOf** always returns a string that represents the type of the value
- when we look at this we are asking, *what is the **type** of the **value currently in v***
- **var v;**  
    -typeOf v;
    - // "undefined"
- **v = "1";**
    - typeOf v;
    - // "string"
- **v = 2;**
    - typeOf v;
    - // "number"
- **v = true;**
    - typeOf v;
    - // "boolean"
- **v = {};**
    - typeOf v;
    - // "object"
- **v = Symbol();**
    - typeOf v;
    - // "symbol"
- **v = undefined;**
    - typeOf v;
    - // "undefined"

### odd ones
- **typeOf null returns an object!** 
- Have to be careful when typeOf is used that it's not infact NULL
    - **var v = null;**
        - typeOf v;
        - // object ***this is strange & a known JS bug***
    - Part of why this bug exists could be:
        - If you want to **unset a numerical value** you use **undefined**
        - If you want to **unset an object reference** you use **NULL**
- **this is odd as the function type is not officially a JS type**
    - **v = function(){};**
        - typeOf v;
        - // "function" 
- **this is odd because why does function tell us its a function but array does not?**
    - v = [1,2,3];
        - typeOf v;
        - "object"??
    - Instead there are other things to help you. We have **array.isArray**
        - this will let you know if its an array.

## Undefined -vs- Undeclared
- **Undefined** 
    - when something doesnt even exist
    - theres definately a variable and at the moment, it has no value
- **Undeclared** its never been created in a scope we have access to
- **Uninitalised**
    - aka TDZ - temporal dead zone
- **NAN** best represented as **AN INVALID NUMBER**
    - nan stands for not a number
        - what its better thought of as is: special sentinal value that represents an invalid number or **invalid number**
    - comes to us in JS from the IEEE 754 numbers specification
    - **NAN is the only value that does not equal it's self.**
    - so if you have 
        - var myCatsAge = Number("N/A"); // NaN
        - myCatsAge === myCatsAge; // False OOPS!!!
#### if you do any mathematical equasion on NAN, it returns NAN
- nan will propagate through your code.



