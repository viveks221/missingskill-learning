
 # Variables
    Variables are containers which are used to store data. variables in javascript are dynamically type.
    i.e they are evaluated on the runtime.Type is defined on the fly
    
  ### Rules for declaring a variable
     - Variable names cannot contain spaces.
     - Variable names must begin with a letter, an underscore (_) or a dollar sign ($).
     - Variable names can only contain letters, numbers, underscores, or dollar sign
     -  Variable names are case-sensitive.
     -  certain words may not be used as variable names, because they have other meanings within JavaScript (reserved words)
         
  ### There are 3 ways to declare a JavaScript variable:
     - using var 
     - using let 
     - using let
     
     
 ### diffrence between let, const , var         
  | var   | let | const |
| ------------- | ------------- |  ------------- | 
| Can be redeclared  | Can not  be redeclared   |  Can not be redeclared             | 
| functional scoepe  | Lexical scope  |  Lexial scope            |    
| can be re-initialised | can be re-initialised   |  can not be re-initialised        |  
 | Hoisted               |   do not get hoisted    |   do not get hoisted               |   
 
 
 
 
 ### Hoisting
 When we declare a variable using the var keyword, the declaration of that variable 
 is put into the memory component of the browser during compile time. 
 That variable is hoisted in the memory. So, if we try to access that variable before its declaration, we won’t get an error.
 
 ```javascript
   console.log (vivek);    // here ouput will not be undenfined as variable vivek gets hoisted
  
   var vivek=8;
   
   ```
   
   
   
 ### Type conversion and Type coercion
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
      
 ### Truthy and Falsy value
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
    
### Scopes  
The location where variable is defined dictates where we have access to that variable.
 Types of scope
- Functional scope
    - Variables defined inside a function are not accessible from outside the function.
    - Variables declared with var, let and const are quite similar when declared inside a function.
    -  ```javascript
           
           function hi() {
           const vivek = "hello vivek";
           let sanny = "hello sanny";
           var Hemant = "hello hemant" ;
           console.log(vivek, sanny, hemant); // scope of let const var is limited to function only, we can not call them outside function
           }
           hi();
            console.log(vivek, sanny, hemant); //  refrence error vivek sanny  hemant are not defined 
            
            
      ```
   
- Block scope 
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
     
     
- Lexical scope
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
   
     
   
   
