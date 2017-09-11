## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?
  * A cookie is a tool used to maintain state between requests. Unlike sessions, cookies are client-side files that contain user information. You can store information like a username in a cookie, which you would hand over to the server which would grant you authorization to certain pages or user-specific information (like items in your shopping cart).
* What’s the difference between a session and a cookie?
  * As mentioned before, cookies are client-side files, which make them insecure and unreliable. Since clients/users can manipulate the cookie before handing it back to the server, sessions are a more preferred way to handle authorization and authentication because the server will store the pertinent information in a session object, create a session id, which is then given to the user as a cookie. The next time the user hands back the cookie to the server, the server looks up the session id attached to the cookie and will grant access accordingly.
* What’s a flash and when do you want to use flashes?
  * Flash is data that will only last for one request (unlike a session which will last as long as the cookie does not expire). You may want to use flash when you want to relay a message momentarily. Say, for example, after a user successfully creates an account and is redirected to their show page, you want to flash them a message that their account has been successfully created. You can do that with a flash message.
* Why do people say “HTTP is stateless”?
  * HTTP is a stateless protocol because it doesn't retain any memory ("data") of interacting with you, the user, or any users for that matter. The connection between the browser and the server is lost once the transaction ends. Every time I visit Facebook, Facebook will treat me like a new visitor UNLESS I give Facebook a session cookie.
* What’s authentication? Explain.
  * Authentication is a measure taken to protect users accounts (and in turn, their identity and personal information). It confirms that the user him or herself is who they say they are.
* What’s the difference between authentication and authorization?
  * Although you may be you who you say you are, you may have restricted access to certain pages on a website. Typically, a regular user will not have access to certain methods, or another person's show page, and that is where authorization comes in. It sets restrictions on the user and limits their privilege. Unless they are granted access, they may be redirected elsewhere or shown an error message.
* What’s a before filter?
  * The `before_filter` will run the method you indicate right before it runs anything else.
* How do we keep track of a user once they’ve logged in?
  * Through our helper method, `current_user`.
* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
  * You would want to namespace a resource when you want to grant authorization to a group of users (for example: admins) to do certain things (like `delete` or `create` objects/rows).
  * You would want to nest a resource when there is a relationship between the parent resource and child resource (the URI will typically look like this: `/users/1/gifs`).
* At a high level, what tools can you use to implement authorization? How would you use them?
  * `before_action`
  * enums
  * `current_admin?` and `require_admin` method
  * I would first create enum roles to would differentiate my users (you can either be a default user or an admin). In the `AdminController`, I would restrict access to anyone who is not an admin by calling `before_action: require_admin`, which will grant authorization if the method returns true (you are an admin) or render a 404 if it returns false (you are not).
* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
  * An enum is an attribute where the values map to integers in the database.
  * With enums, you can create different user roles (default, admin, super admin).
  * To use an enum, you will first have to add a column to your table (`role:integer`). This will store the integer. In the model, you will declare the enum by mapping the integer to its respective value (`enum role: %w(default admin)`).
* What are some strategies you can use to keep your views DRY?
  * Using `render`, `redirect_to`, partials, and form helpers.
