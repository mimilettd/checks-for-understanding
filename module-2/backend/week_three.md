## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?

```
rails new <name> -T --database=postgresql --skip-spring --skip-turbolinks
```

2. What do Models generally inherit from in rails?
  * ApplicationRecord
3. What do Controllers generally inherit from in a rails project?
  * ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes title assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

```
resources :horses, only: [:show]
```

5. What rake task is useful when looking at routes, and what information does it give you?
  * `rake routes` will show you the Prefix, Verb, URI pattern, and Controller#Action.
6. What is an example of a route helper? When would you use them?

```
category_path(category)
```

  * I would use them when I need to link my text or button to another page on my website.
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

```
companies_url => http://localhost:3000/companies
companies_path => /companies
```

8. What are strong params and why are the necessary?
  * Strong params allow us to take a greater control over the sanitizing process when it comes to user input. Through strong params, we can whitelist specific keys by indicating the following in our code:

```
params.require(:user).permit(:username)
```

9. What role does `form_for` play in helping us create our forms?
  * `form_for` creates a form in rails that allows the user to create or update the attributes of a specific model object.
10. How does `form_for` know where to submit the user's input?
  * By passing it an instance variable, it knows what object to create/update.
  * The helper knows if it should create a new record or update an existing record based on where the form is living (new.html.erb which talks to the new method in the Controller or edit.html.erb which talks to the edit method in the Controller).
11. Create a form using a `form_for` helper to create a new `Horse`.

```
<%= form_for(@horse) do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  <%= f.label :age %>
  <%= f.text_field :age %>
  <%= f.submit %>
<% end %>
```

12. Why do we want to validate our models?
  * To ensure that only valid data is saved into our database. Say for example we want every user to input a valid email address. Rails will not allow the user to create an account unless an e-mail is entered by doing `validates :email, presence: true`.
