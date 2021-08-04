
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
    ```javascript 
    
    var vivek = 8;
    console.log (vivek);
   
