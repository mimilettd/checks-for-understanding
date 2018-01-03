## Week Four - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's your favorite project management tool?
  * PivotalTracker
2. Why do we create staging environments?
  * We create staging environments to test that our code works in a "production-like environment". Meaning, if it doesn't, we still have an opportunity to debug and fix our code before it goes live. 
3. What are the characteristics of a good README (in your opinion)?
  * Title
  * Getting Started
    * Prerequisites
    * Installing
  * Running tests (how-to)
  * Deployment
  * Built With (Technology Stack)
4. What's one main improvement you're going to make to your code regarding accessibility issues?
  * Navigation, such as tab-through order (for example, for people with disabilities, it’s extremely important that sites can be navigated using only a keyboard)
5. What are some basic security concerns to be aware of when building applications?
  * Man in the Middle - any attacks that involve modifying the communication between a client and server
  * Replay - Replay attacks store your traffic to play it again later
  * Clickjacking - employed on malicious websites to make you do things on other websites.
  * Injection - Injection causes your site to execute some instruction while trying to work with data
6. Why is continuous integration helpful/important?
  * Continuous integration is helpful because it requires members of a team to integrate their work frequently into a shared repository several times a day. Each check-in is then verified by an automated build, which allows the team to detect integration errors as quickly as possible.
7. What are some pros/cons of using ReactJS as a frontend tool?
PROS:
  * Virtual DOM in ReactJS makes user experience better and developer's work faster
  * ReactJS permits reusing code components - significantly saving time
  * One direction data flow in ReactJS provides stable code
CONS:
  * High pace of development - Facebook developers are making updates to ReactJS every two weeks.
  * Poor documentation

#### Review  

8. What are some characteristics of "good" git workflow?
  * Everything on `master` is deployable
  * When you create a branch in your project, you're creating an environment where you can try out new ideas
  * Branch names should be descriptive
  * Each commit is considered a separate unit of change.
  * Make a pull request when you're ready to merge your feature to master. NOTE: PRs are also a great time to initiate discussion about your commits.
  * Once your pull request has been reviewed and the branch passes your tests, you can deploy your changes to verify them in production. 
  * Once your changes have been verified in production, your teammates can  merge your code into the master branch.
9. Describe each of the four fundamental concepts of object oriented programming.
  * Abstracton - hides all but the relevant data about an object in order to reduce complexity and increase efficiency
  * Encapsulation - the process of combining data and functions into a single unit called class. Furthermore, the data is not accessed directly; it is accessed through the functions present inside the class.
  * Inheritance - enables new classes to receive-or inherit-the properties and methods of existing classes.
  * Polymorphism - the ability to take into different forms or stages.
10. What's a module in Ruby? What's the difference between a class and a module? What are some good use cases for modules?
  * In Ruby, modules provides methods that you can use across multiple classes, whlie classes lay the blueprint to create an object (or multiple objects)
  * Authentication and authorization systems are good examples of modules. Authentication systems work across multiple app-level classes (users are authenticated, sessions manage authentication, lots of other classes will act differently based on the auth state). You would typically choose a module over a class if what you're trapping to encapsulate is stateless.
