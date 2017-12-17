## Week Three - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. At a high level, what is Node?
  * Node is a run-time environment that allows developers to create server-side tools and applications in JavaScript.
2. What is Express? What is Express similar to in the Ruby world?
  * Express is a lightweight, unopinionated web framework built on top of Node.
  * Express helps simplify and organize the server-side functionality by abstracting the more confusing components of Node.
  * Express offers an MVC architectural pattern similar to Rails, for example:
    * Mechanisms to write handlers for requests with different HTTP verbs at different URL paths (routes)
3. How do we setup a route when creating an API with Node and Express? Please provide a code snippet.
```javascript
app.get('/', function(request, response) {
  response.send('Hello World!')
})
```
4. What do we use Knex for?
  * We use Knex to work with our database.
  * For example, with Knex, we can create, migrate, and seed our PostgreSQL database. We can also inject SQL statements using `.raw()`.
5. How **could** you organize your code to follow the MVC design pattern in your Quantified Self project?
  * Have all the handlers for requests with HTTP verbs live in `server.js` (controller)
  * Abstract and encapsulate the logic of the application into `lib/models` (models)
  * Output the information via `.html` files.
6. How do you execute raw SQL in node?
```javascript
database.raw(
  'INSERT INTO foods (name, calories, created_at, updated_at) VALUES (?, ?, ?, ?)',
  ["Banana", 150, new Date, new Date]
)
```
7. What are some advantages to having your front end and back end code live in separate applications? What are some disadvantages?

[ADVANTAGES]

  1. Modularity: If you have your application logic (backend) completely seperated from your application user interface (frontend), you will have a slightly more modular web application. This will aid in a number of things, for example: testing, readability, and maintainability.
  2. Reusability: With a separate backend, your API can be reused with a number of applications (not just the front-end you originally planned for).

[DISADVANTAGES]

  1. Time: Building one application takes some time, let alone two. You will have to plan accordingly and make sure that both applications are set up correctly to talk to each other. 

#### Review  

8. Describe DNS.
  * DNS stands for Domain Name Servers.
  * They maintain a directory of domain names and translate them to Internet Protocol (IP) addresses.
  * For example, when I type "google.com" into the browser, my internet service provider (ISP) will look for the DNS associated to the domain name because my computer is only able to access websites based on IP addresses. Once it finds the DNS associated with "google.com", it will translate it into a machine-friendly IP address and directs your internet connection to the correct website.
9. What does writing clean code mean to you?
  * Don't Repeat Yourself (DRY)
  * Short and concise methods/functions
  * Single Responsibility Principle (SRP)
10. If you were building an application that models hotels, what classes would you need? What classes would be responsible for what functionality? Hint: think about what tables you would need in the database, how those records would relate to each other, and good OOP.
  * I would need a class for hotels, rooms, reservations, guests, and employees.
  * Rooms, guests, and employees belong to a hotel (one to many relationship)
  * Reservations would be the joins table between rooms and guests (many to many relationship)
