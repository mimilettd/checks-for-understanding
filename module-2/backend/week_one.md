## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

1. **List the five common HTTP verbs and what the purpose is of each verb.**
  * GET retrieves data (asks the server for a resource)
  * POST is used to submit data (to the server)
  * PUT takes a complete resource and stores it at the given URL. If there was a resource there previously, it is replaced; if not, a new one is created.
  * DELETE destroys the specified resource (on the server)
  * PATCH can be used to update partial resource(s) (on the server)
2. **What is Sinatra?**
  * Sinatra is a light-weight tool web developers use to build simple and dynamic Ruby web applications.
4. **What is MVC?**
  * MVC stands for Model, View, and Controller.
5. **Why do we follow conventions when creating our actions/path names in our Sinatra routes?**
  * We follow conventions (specifically Restful Routes & CRUD) because it allows us to handle URLs and data manipulation in a consistent manner. Without a specific convention to follow, it would be hard to us to create new content, edit new content, and delete existing content without confusing both users and programmers alike.
6. **What types of variables are accessible in our view templates without explicitly passing them?**
  * Instance variables.
7. **Given the following block of code, how would I pass an instance variable** `count` **with a value of** `1` **to my** `index.erb` **template?**

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
<<<<<<< HEAD

```ruby
get '/horses' do
  erb :index, :locals => {:name => 'Mr. Ed'}
end
```

9. **What's the purpose of ERB?**
  * ERB allows us to combine HTML with Ruby code for variable substitution and flow control.
10. **Why do I need a development AND test database?**
  * I need one for testing purposes and one for development purposes. If I had only one database, not only would I be testing with the data provided in the test, every time I would run the test, I would also be adding the data to my development database. This behavior would pollute my database and therefore interfere with my tests.
11. **What's responsive design?**
  * Responsive design is the approach that web applications should be sensitive to different environments (screen size and platform).
12. **What is CRUD and why is it important?**
  * CRUD stands for (C)reate, R(etrieve), (U)pdate, and (D)estroy. CRUD a very important acronym that refers to all of the functions that are implemented when a database is involved.
13. **What does HTTP stand for?**
  * Hypertext Transfer Protocol.
14. **What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?**
  * `<%= code %>` is an expression-printing tag that executes the code and prints it.
  * `<% code %>` is a non-printing tag that executes the code but does not print it.
15. **What's an ORM?**
  * ORM stands for Object Relational Mapping. It is a technique used for managing and interacting with data coming from incompatible data sources.
16. **What's the most commonly used ORM in ruby (Sinatra & Rails)?**
  * ActiveRecord.
17. **Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.**

| **URL** | **HTTP Verb** |  **Action**|   **Explanation**|
|------------|-------------|------------|------------|
| /restaurants/         | GET       | index | See all restaurants.  
| /restaurants/new         | GET       | new | See form to enter a new restaurant.  
| /restaurants          | POST      | create | Submit form to create a new restaurant.  
| /restaurants/:id      | GET       | show | See one restaurant.      
| /restaurants/:id/edit | GET       | edit | See form to update a restaurant.      
| /restaurants/:id      | PATCH/PUT | update | Submit form to update a restaurant.   
| /restaurants/:id      | DELETE    | destroy | Delete a restaurant.

18. **What's a migration?**
  * A migration allows us to create or modify a table in ActiveRecord.
19. **When you create a migration, does it automatically modify your database?**
  * When I create a migration (`rake db:create`), it does not automatically modify my database. To modify my database, I have to also run `rake db:migrate`.
20. **How does a model relate to a database?**
  * Via tables.
21. **What's the difference between agile workflow and waterfall method?**
  * An agile workflow is iterative while a waterfall is not. While agile emphasizes rapid delivery of an application in complete, functional components (sprints), waterfall typically waits until one stage is done before the project moves onto the next stage.
22. **What is the difference between** `#new` **and** `#create`**?**
  * `new` creates a new instance of an object but will not save it unless you call `save` after.
  * `create` creates a new instance of an object as well as saves it to the database.
