## Week Two - Module 2 Recap

Fork this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  * ActiveRecord is an ORM (Object Relational Mapping framework) that allows us to create models, make associations/relationships between these models, and perform database operations using Ruby.
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

`fetch`, `where`, and `find_by` are examples of methods we can call on `Team`. These methods are inherited from the module ActiveRecord.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

```ruby
team = Team.find(4)
team.name
```

```ruby
team = Team.find(4)
owner = Owner.find(team.owner_id)
```

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

```ruby
team = Team.find(4)
team.owner

```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

<img src="http://i.imgur.com/MYu34Aj.png">

6. Define foreign key, primary key, and schema.
  * A foreign key is a field in one table that refers to the primary key located in another table. A primary key is the object's `id`. A schema shows the current state of the database. When you create a table (`rake db:create migration NAME=<table_name>`) and migrate it (`rake db:migrate`), the schema will update accordingly.
7. Describe the relationship between a foreign key on one table and a primary key on another table.
  * A foreign key on one table indicates its' relationship with the primary key on another table (it can be a one-to-many, one-to-one, or many-to-many relationship). Using the example above, a team can belong to an owner and an owner can have many teams. This is a one-to-many relationship. When we specifically indicate this relationship in the `Team` and `Owner` class, we're instructing Ruby to create a foreign key column on the `Team` table using the unique primary key located in the `Owner` table.
8. What are the parts of an HTTP response?
  * Protocol/Version, Status Code, and its Description
  * HTTP Response Headers
  * HTTP Response Body


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
  * `find` retrieves the object corresponding to the specified primary key.
  * `where` retrieves the object corresponding to the specified attribute.
  * `order` sorts your records (ascending and descending)
  * `pluck` returns an array of values corresponding to the argument.
  * `create` creates a new object and saves it - all in one step. Yay!
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
  * `rake routes` gives you a list of routes in your application.
  * `rake db:create` creates your database.
  * `rake db:migrate` runs the migrations which haven't been run yet.
3. What two columns does `t.timestamps null: false` create in our database?
  * `created_at` and `updated_at`
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
  * one-to-many (a school has_many teachers, a teacher belongs_to a school)
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

<img src="http://i.imgur.com/tgp0Xcv.png">

6. Give an example of when you might want to store information besides ids on a join table.
  * I don't know. I'm curious, though! What might I want to store aside from ids in a join table?
7. Describe and diagram the relationship between patients and doctors.
  * many-to-many relationship (a doctor can have many patients and a patient can have many doctors)
  * in ActiveRecord, we would describe this relationship with the following code:

  ```ruby
  class Doctors < ApplicationRecord
    has_many :appointments
    has_many :patients, through: :appointments
  end

  class Appointment < ApplicationRecord
    belongs_to :doctor
    belongs_to :patient
  end

  class Patient < ApplicationRecord
    has_many :appointments
    has_many :doctors, through: :appointments
  end
  ```

<img src="http://i.imgur.com/3qqykQd.png">

8. Describe and diagram the relationship between museums and original_paintings.
  * one-to-many relationship (a museum can have many original paintings but an original painting can only belong to one museum).
  * in ActiveRecord, we would describe this relationship with the following code:

  ```ruby
  class Museums < ApplicationRecord
    has_many :original_paintings
  end

  class OriginalPaintings < ApplicationRecord
    belongs_to :museum
  end
  ```

9. What could you see in your code that would make you think you might want to create a partial?
  * Repeated code.
