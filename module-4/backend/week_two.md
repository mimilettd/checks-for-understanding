## Week Two - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's one difference between ES5 and ES6?

|                       | ES5                                        | ES6                                                        |
| --------------------- |:------------------------------------------:| ----------------------------------------------------------:|
| semi-colons           | required                                   | not required                                               |
| variable declarations | `var`                                      | `let`, `const`                                             |
| string interpolations | `"string" + variable`                      | back ticks + `${variable}`                                 |
| defining functions    | `function(v){}`                            | `v=>{}`                                                    |
| defining classes      | `function Cat (name) { this.name = name }` | `class Cat { constructor (name) { this.name = name } }`    |

2. What's the difference between asynchronous and synchronous JavaScript? 
  * JavaScript runs synchronously, meaning it can only execute a single thread. Because our browser provides multi-threads, however, JavaScript is able to run asynchronously through `callbacks` and `promises`.
3. What are the four pillars of Object Oriented programming?
  * Abstraction - hides all but the relevant data about an object in order to reduce complexity and increase efficiency.
  * Encapsulation - the process of combining data and functions into a single unit called class. Furthermore, the data is not accessed directly; it is accessed through the functions present inside the class.
  * Inheritance - enables new classes to receive—or inherit—the properties and methods of existing classes. 
  * Polymorphism - the ability to take into different forms or stages. For example, a subclass can define its own unique behavior and still share the same functionalities or behavior of its parent/base class while a parent class cannot have the behavior of its subclass.
4. What are some tools available in JavaScript to help you write object oriented code?
  * Class - JavaScript allows us to abstract and encapsulate our functions in a class (`class Dog { constructor (name) { this.name = name} }`). In turn, we can construct as many objects of this class by invoking `new` (`var jake = new Dog('Jake')`)
  * Prototype - Javascript allows us to inherit functions from parent classes (polymorphism)
5. What are some key concepts to be aware of when refactoring your JavaScript?
  * DRY - Don't Repeat Yourself!
  * SRP - Is this function doing one thing?
  * Function names - Is this function describing exactly what it's doing?
6. What's a callback function and what are some reasons when we use/need callback functions?
  * A callback function is a function that is passed to another function as a parameter. The callback function is called inside that function.
  * Callback functions are required when we use JQuery; for example:
  ```
  $("#btn_1").click(function() {
    alert("Btn 1 Clicked");
  });
  ```
  * Above, we are passing a function through `click`, and that function will excute the alert "Btn1 Clicked" if the button with an ID of `btn_1` is clicked.
  * When we are using a prototype method like `forEach`, `filter`, `map`, and more, we need a follow up with a callback function.
7. What are the different scopes of variables in Javascript? When would you want to define global variables?
  * `var` - Scoped to its current execution context, which is either the enclosing function or, for variables declared outside any function, global. For example:
  ```
  function() {
    var x; // local scope 
  }
  ```
  ```
  var x = "World" // global scope
  function hello(x){
    console.log(`Hello ${x}`);
  }
  ```
  * `let` - Limited in scope to the block, statement, or expression on which it is used. 
  * `const` - Scope can be either global or local to the block in which it is declared. Most importantly, the identifier of the constant cannot be reassigned (though not to be confused with immutable -- if the constant is an object, the object's contents can still be altered)
  * For the most part, it is best practice to declare local variables. One situation in which you would use global variables is when requiring another file to access its functions (for example, `const FilterTable = require('../helpers/FilterTable')`)
8. What's the difference between `==` and `===` in JavaScript?
  * `==` is an abstract equality comparison while `===` is strict equality comparison.
  * `==` converts both values to a common type and then compares the two while `===` does not.
9. Why do front end frameworks exist?
  * Frontend frameworks exist because there are no "built-in" module for front-end development.
  * It keeps state out of the DOM
  * Instead of 'reinventing the wheel' everytime, frameworks offer a way to share common concepts, tools, and knowledge among developers and teams.

#### Review  

10. Why do people say "HTTP is stateless"?
  * HTTP is called a stateless protocol because each command is executed independently, without any knowledge of the commands that came before it.
  * When I visit `google.com`, Google does not retain the state of my previous request.
11. Describe a RESTful API.
  * A RESTful API is an appliation program interface that uses HTTP requests to GET, PUT, POST, DELETE data.
  * REST is the underlying architectural principle of the web. It stands for Representational State Transfer.
  * An API that adheres to the principles of REST does not require the client to know anything about the structure of the API. Rather, the server needs to provide whatever information the client needs to interact with the service
12. What are some main characteristics of a team following an agile workflow?
  * Teams work in iterations
  * Frequent inspection and adaptation are encouraged.
  * Teams hold daily stand-ups
13. What are some advantages **and** disadvantages to using OAuth to authenticate a user?
  * Advantage: Convenience. Instead of having the user enter the same information every time to create and sign into their account, they can authorize the web app to use Facebook, Twitter, Google, etc, to authenticate their identity.
  * Disadvantage: If you created an account using Facebook OAuth, you will have to continue logging in with Facebook to access your account as the two are tied.
