1. How do we make flash messages display on a page?
  * There are a couple ways we can display flash messages on a page. If we wanted to have them rendered on a specific ERB page, we can do `<%= flash[:message] %>` at the top. Another way is to include the code in the  `application.html.erb` page:

```
<% flash.each do |name, msg| %>
      <%= content_tag :div, raw(msg), class: name %>
    <% end %>
```

2. Where is cart information/temporary information usually stored?
  * In a session cookie.

3. What might be some reasons not to store cart in our database? Are there any reasons why we would want to persist that information?
  * We might not want to store the cart in our database for the following reasons: (1) users may change their mind regarding a specific item and when they remove it from their cart, this information would have to be dropped from our database; (2) visitors can also place items in their cart without logging in so should this information be stored in our database, we would have to find a way to tie the `cart` information to that unique visitor. **Note to self** How would we do this?
  * We might want to persist this information if we want a history of items users have added into their cart and use that information for analytics.

4. What is the purpose of the asset pipeline?
  * The asset pipeline is a combination of folder paths for Rails to look for assets in. It concatenates and minifies JavaScript and CSS assets. It also adds the ability to write these assets in other languages and pre-processors such as ERB.

5. Why do we precompile our assets?
  * We precompile our assets so that we don't end up deploying assets that we don't want deployed.

6. What do each of the following tags do?

```
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

  * Looks in our `assets/stylesheet` folder for an `application` file.
  * Looks in our `assets/application` folder for an `application` file.
  * Renders an image located in our `assets` folder with the name `rails.png`

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
  * Elements of a great read me for projects include a brief high level synopsis on what the project is about, what they accomplished, some challenges they experienced and the language they wrote their code in.
  * Elements of a great read me for gems, tutorials, or the like, include a table of contents and a section for instructions/installation steps and known issues.

8. What are the top four accessibility issues that we as developers should be aware of?
  * Mobility
  * Cognitive, mental, or emotional impairment
  * Vision impairment
  * Hearing impairment

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

  * `before_save` is an ActiveRecord callback and is used to execute a block of code before the object is saved. This lives in our model.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

```ruby
scope :active, -> { where(active: true) }
```

11. What is the difference between a scope and a class method?
  * Scopes allow you to define and chain query criteria in a declarative and reusable manner. Scopes are a great way to grab the right objects out of our database
  * Class methods allow us to mix Ruby code with database code to retrieve the information we want.
