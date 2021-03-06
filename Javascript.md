# Introduction
 - JavaScript was invented by Brendan Eich in 1995.
 -  It was developed for Netscape 2.
 -  It was developed in 3 weeks
 -  javascript = java + livescript

# Tech debt  
  - ==  only check value of number not datatype. so === was introduce.
  - typeof(null) = object : it was too late to make changes, ideally typeof(null)= null.


# Data types
- Basically there are 2 types of data types  
     - Primitive 
         - String : anything enclose in " " is a string
         - Number
         - Boolean : true or false
         - Undefined : when variable is declared but we dont ssign any value then type of that variable is undefined
         - Null   : empty/ zero
         - Symbol
     - Non-primitive 
         -  Objects: objects are basically key value pairs
         -  Array: arrrays are also objects here keys are the indices
        



 # Variables
    Variables are containers which are used to store data. variables in javascript are dynamically type.
    i.e they are evaluated on the runtime.Type is defined on the fly
    
  ## Rules for declaring a variable
     - Variable names cannot contain spaces.
     - Variable names must begin with a letter, an underscore (_) or a dollar sign ($).
     - Variable names can only contain letters, numbers, underscores, or dollar sign
     -  Variable names are case-sensitive.
     -  certain words may not be used as variable names, because they have other meanings within JavaScript (reserved words)
         
  ## There are 3 ways to declare a JavaScript variable:
     - using var 
     - using let 
     - using const
     
     
 ## diffrence between let, const , var         
  | var   | let | const |
| ------------- | ------------- |  ------------- | 
| Can be redeclared  | Can not  be redeclared   |  Can not be redeclared             | 
| functional scoepe  | Lexical scope  |  Lexial scope            |    
| can be re-initialised | can be re-initialised   |  can not be re-initialised        |  
 | Hoisted               |   do not get hoisted    |   do not get hoisted               |   
 
 
 
 
 # Hoisting
 When we declare a variable using the var keyword, the declaration of that variable 
 is put into the memory component of the browser during compile time. 
 That variable is hoisted in the memory. So, if we try to access that variable before its declaration, we won???t get an error.
 
 ```javascript
   console.log (vivek);    
  
   var vivek=8;
   
   ```
   
   
   
 # Type conversion and Type coercion
  - when we manually convert from one type to another is caaled type conversion
      ```javascript
           let a= Number("10"); // manually converting string to a number
           let b= 10;
           console.log(a+b);   // otput =20
      ```
      
  - when javascript automatically covert types behind the scenes for us is  called type coercion
      ```javascript
      let a= "10" ;    
           let b= 10;
           console.log(a+b);   // one of the operand is string so javascript automatically converts other operands to string   // output 1010
          
          
      ```
      
 # Truthy and Falsy value
   - There are only 5 falsy values except these 5 values all are truthy values
    - 5 Falsy values are; 0, '', undefined, null, NaN
          
   ```javascript
         
             console.log(Boolean(0));           // output will  be false 
             console.log(Boolean(undefined));  // output will  be false 
             console.log(Boolean(null));        // output will  be false 
             console.log(Boolean(Nan);         // output will  be false 
             console.log(Boolean(''));          // output will  be false 
             console.log(Boolean({}));           // output will  be True
             console.log(Boolean([]));          // output will  be true  
  ```    
    
# Scopes  
The location where variable is defined dictates where we have access to that variable.
 Types of scope
### Functional scope
    - Variables defined inside a function are not accessible from outside the function.
    - Variables declared with var, let and const are quite similar when declared inside a function.
  ```javascript
           
           function hi() {
           const vivek = "hello vivek";
           let sanny = "hello sanny";
           var Hemant = "hello hemant" ;
           console.log(vivek, sanny, hemant); // scope of let const var is limited to function only, we can not call them outside function
           }
           hi();
            console.log(vivek, sanny, hemant); //  refrence error vivek sanny  hemant are not defined 
            
  ```
   
### Block scope 
   - variable declared by let const are block scoped. we can not acees them outside the block where they are defined.
      ```javascript
      function fruits() {
         if(true) {
         var fruit1 ="apple";
         let fruit2 =" banana"
         const fruit3 ="orange"
         console.log(fruit1,fruit2,fruit3);  //fruit2 fruit3 are scoped to this block only we cannot call outside this if {} block.
         }
          console.log(fruit1); // vaiable declred wit has function scope so we can call it inside function
      console.log(fruit2);   // at this line there will refrence error as fruit2 varible is block scoped
      console.log(fruit3);   // at this line there will refrence error as fruit3 varible is block scoped
        
      }
      fruits();
     ```
     
     
### Lexical scope
   Inner function nested inside some parent function has acces to variables define inside the scope of its parent function.
   But the reverse is not true.
   
  ```javascript
   function fruits(){
   const fruitsName=["apple","mango", "orange"]
   console.log(hello);                                // at this there will be an reference eerror as parent can not acess varible declared in its child
      function childOfFruits(){
      var hello = "hi";
      for(let name of fruitsName){
      console.log( `eat it its full of nutrients, ${name}`);   // fruits name is defined in scope or fruits function. so it child can acees it 
         }
       }
       childOfFruits();
    }  
      
   ```
   
 # Logical Operator
 
   | Operator | Description | |
| ------------- | ------------- |  ------------- | 
| && | Logical AND   |  a&&b output is true when both a and b are true    | 
| // | Logical OR   |  a//b output is true when either a or b is true            |
| !   | Logical not  |   !a if is a true it changes it to false                    |



# Copy by value and Copy by refrence
  ### All prmitive types are copy by value 
     - Analogy of copy by value is xerox. Both the variable will exactly same
     - changes made in one variable do not affects the other variable
  ```javascript
           var a="hello";
           var b=a;
           var a="bie";
           console.log(a,b); // outbput bie hello. No change in b
  ```
        
        
  
  ### All non primitive types are copy by refrence
     - A variable assigned to an object stores not the object itself, but its ???address in memory??? ??? in other words ???a reference??? to it.
     - changes made one variable will reflect  the other variable 
```javascript
            var abc={}
            var cde=abc
            abc.hlo="bie"
            console.log(abc, cde)
            // output will be {hlo: "bie"} , {hlo: "bie"}  changes made in abc affects cde
           
```
# Functions
 -A JavaScript function is a block of code designed to perform a particular task.
 - In Javascript Function are reffred as first class citizen.
 - A function can be assigned to a variable
 - Function can return another function.
 - Function can be passed as parameter to another function.
 - ** Function declration gets hoisted **
 - function gets override if you rediifine it.
 
 
    ### Function declaration 
```javascript
     function fn_name(){


       //here write the code to be executed

     } 
     fn-name(): // function call


```

### function hoisting
   - Only function declration gets hoisted not assignment.
  - it is quite similiar to variable hoisting.
  - here complete block gets hoisted.

```javascript
      hello(); //  we can call hello function 
       function hello(){
       console.log(" hi");
       }
       
 ```
   
   
 ### Function assingnment
```javascript
       hello(); //  we cannot call hello function as here var a gets hoisted not the function 
       console.log(a); // a can be calle as it gets hoisted
       var a = function hello() {   // assignment of function to a variable
       console.log(" hi");
       }
       
 ```
   
# Higher order functions
    -Any functions which takes functions as prameter or return a function are called higher order functions

```javascript
function score(func) {
func();
func();
}
  fuction param(){
  var a= Math.floor(Math.ramdom() * 10);
  console.log(a);
  }
  
  score(param);   // function pass as prameter
  
  
 // function returning another function
   function double(params) {
   console.log"(print" + params)
       
       function inner(){
       console.log(params *2)
       }
       return inner ;
  } 
  var a==90;
  double(a);
  
 






```
# Immediately invoked function(IIFE)/Self executing function(SEF):
  -They only runs once.
  - They are the anonymous function i.e without name

```javascript
     (function(){
        console.log (" iife function");
      })
        (); // calling iife/anonymous function
 
```


 
 # ARROW FUNCTIONS
 -Newer  version of definig functions
 - syntactically compact alternative to a regular function expression
 - It is function assignment so not gets hoisted
 - if only 1 parameter is passed we can avoid paranthesis.

```javascript
     var b =() =>{
     console.log("arrow");
     }
     b();
     
 ```
 
 # string methods 
   ### Length
   ### slice()
   ### replace()
   ### toUpperCase()
   ### tolowerCase()
   ### concat()
   ### trim()
   ### charAt()
```javascript
 var a= " hello world ";
 a.length // length= idicies+1
 a.slice(0,6)  // slice from indice 0 to 5
 a.replace("hello", "hi")  // replace hello with hi
 a.toUpperCase // convert string to uppe case
 a.tolowerCase // convert string to lower case
 a.concat(a, "1") // concat hello world 1
 a.trim()     // trim space from statr and end
 a.charAt(4) // prints caharacter at indice 4
```

# Array methods
  -Popping
   -The pop() method removes the last element from an array:
```javascript 
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.pop();  // Removes "Mango" from fruits 
```
  # Pushing
    -The push() method adds a new element to an array (at the end)
    
 ```javascript   
    
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.push("Kiwi");   // Adds "Kiwi" to fruits
 ```
 
    
  # concat
   The concat() method creates a new array by merging (concatenating) existing arrays.
   
   
```javascript  
      const myGirls = ["vivek", "sanny"];
      const myBoys = ["hemant", "abhay", "shantanu"];

      // Concatenate (join) myGirls and myBoys
      const myChildren = myGirls.concat(myBoys);
 ```
 
 # shift()
   -The shift() method removes the first array element and "shifts" all other elements to a lower index.
   
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift();   // Removes "Banana" from fruits
```

# unshift()
 - unshift() method adds a new element to an array at the beginning.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon");    // Adds "Lemon" to fruits in the begining

```

    
    
 # Built in functions in javascript
   ### setTimeout()
      -Used to delay the expression
 ```javascript
     let readEmail= function() {
    var store_email =  prompt( " Enter your email adress");
     }
     setTimeout(readEmail, 5000 );  // promopt enter your email adreess after 5 seconds
 ```  
   ### setInterval()
       - he setInterval() method calls a function or evaluates an expression at specified intervals (in milliseconds).
        - The setInterval() method will continue calling the function until clearInterval() is called.
        
 ```javascript
     let readEmail= function() {
    var store_email =  prompt( " Enter your email adress");
     }
     setInterval(readEmail, 5000 );  // promopt enter your email adreess after everey 5 seconds
 ```  
 
 # parseInt() Function
   - it convert strings into integer value
   - Not advise to use when dealing with airthmetic operators. 
```javascript
     const num ="10.9"
     let intNum= parseInt(num);
     console.log(intNum); // output 10
```
  
  
  # parseFloat() Function
    - It converts string into floaating point numbers.
    
```javascript
     const num ="10.9"
     let intNum= parseFloat(num);
     console.log(intNum); // output 10.
```

# JSON 
 -javascript object notation
 - JSON is a format for storing and transporting data.
 - JSON is often used when data is sent from a server to a web page.
 - The JSON syntax is derived from JavaScript object notation syntax, but the JSON format is text only. 
 - Code for reading and generating JSON data can be written in any programming language.
 
 
 
# NEW Javascript features
  ### string template literals
```javascript
var a=10
 var b =20
 console.log(` hello age of the person is ${a+b}.`); // hello age of the person is 30
 
```


# Spread operator
 -  It takes in an iterable (e.g an array) and expands it into individual elements.
 - it is used when we want to create a copy and we dont want changes made in copy affects the original one.
 - if array consist items which are non primitive then changes made in that  non primitive will affect its copy too.
``` javascript
let a = [ 1,2,3,4, 5]
console.log(a);            // this will log entire array. output   [1, 2, 3, 4, 5]
console.log(...a);         // this will log individual items of aray  output 1 2 3 4 5  
let b = a;
a.push(6);
console.log( a,b)  //  we only added 6 to a but it also gets added to b as array are reference type
 // we can prevent it by using spread operator
 let c = [ 7,8,9]
 let d = [...c]
 c.push (10);
 console.log (c,d); // 10 is only added to c not added in d
 
 ```
 # spread with objects
  - it works same as spread with arrays but there is a catch
  <p> spread operator won???t do a deep copy, but it would take each of the elements in the original object/list
 and would map them to a new position in memory. However, if one of the elements happened to be a reference to 
 another object, it will simply make a copy of the reference into memory. </P> 
 
```javascript

let a = {
username: "vivek" ,
userid: " hlo" ,
followers: {
 id:"sanny"
   }
 }
 let b={...a}
 a.followers.id = " hemant",
 console.log(a,b); // hera both and b will be same beacuse followers is of refrence type.so it makes copy of refrence in memory.  
 a.username = "shantanu";  // since username is not refrence typecso changes made a will not reflect in b
 console.log(a,b);
 
```
 





  
  
    
    
    
        
        
     
     













 





 
            |   
   
     
   
   
