## Week One - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's the most useful thing you learned from completing the intermission week work?
  * How to declare variables and write functions.
  * Objects, This, Data Structures
2. What are some tools to help debug JavaScript code?
```
console.log()
debugger
```
Using the following panels in Google Chrome's developer tools:
  * The Elements Panel
  * The Sources Panel
  * The Network Panel

3. What are some tools you need in order to unit test your JavaScript?
  * Mocha (test framework) and Chai (assertion library)
  * Instead of interacting with a server, we can "mock" the interaction using the Sinon library

4. What is the syntax for invoking a function? Give an example.
```
function myFunction(a, b) {
    return a * b;
}
myFunction(10, 2);
```
5. What's `this` in JavaScript?
  * `This` refers to the context in which a function was invoked in JavaScript.
  * By default, `this` refers to the global object in all global code.
  * `This` can also refer to the parent object inside function code (almost like Ruby's `self`).
  * Lastly, `this` in function code invoked using the new operator refers to the newly created object.

6. What is Webpack and why is it useful?
  * Webpack is a Node package that digs through your assets, finds dependencies, and spits out a single JS file that is ready for production. 
  * Webpack is useful because with Webpack, you have access to loaders which preprocess your assets (like fonts, Sass, images, CSS, SVGs etc) and output exactly what your browser needs to know in the smallest package possible.
  * `webpack-dev-server` (a feature of Webpack) is convenient because it executes Webpack whenever you refresh your browser.

7. When/why do you want to use event delegation?
  * You would want to use event delegation when you are trying to target a parent's child elements.
  * For example, for the project Quantified Self, I used an event delegation on the `<tbody>` element because I wanted to target the `<tr>`'s within.

8. What's `npm` and what do we use it for?
  * `npm` is a package manager for the JavaScript programming language.
  * It is a command-line utility for interacting with an open-source repository that aids in package installation, version management, and dependency management
  * We've used `npm` to install tools like `mocha`, `chai`, and `webpack`.

#### Review  
9. What's the MVC design pattern? Describe each part of MVC.
  * MVC stands for `model-view-controller`
  * Logic lives in the `Model` (methods, functions). Its responsbility is to store and manipulate state, typically in a database of some kind.
  * The `View` is a presentation filter -- what the user sees. It renders the model to the user.
  * The `Controller` is the link between a user and the system. The controller decides what the user's input was, how the model needs to change as a result of that input, and which resulting view should be used.

10. What are a few ways to optimize a Rails application?
  * Using indices in our tables.
  * Remove N+1 Queries using `includes`
  * Use Static Storage for Frequently Queried Static Data
  * Caching

11. What's a background worker? When would we want to use a background worker?
  * Background workers perform jobs that are scheduled outside the original request/response cycle
  * We use background workers, like `Active Job`, for long-running requests that may tie up server resources and slow down our server's response time.
  * Background workers can be used for data processing, 3rd Party APIs, maintenance, and email.
