### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
	- ActiveRecord is an ORM
	- it allows you to map:
		- classes --> tables
		- objects --> rows
		- attributes --> column headers

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```
What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?    

- `Team`inherits from ActiveRecord and therefore has access to AR's methods including but not limited to: find, order, group, select, where...etc.


3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4?  Assuming your class only included the code from question 2, how could you find the owner of the same team?
- ```ruby
	Team.find(4)
	Owner.find_by(team: team)

	```
4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

```ruby
Team.find(4).owner
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
![students teachers](https://cl.ly/353k0t3b3c2K/Screen%20Shot%202018-07-07%20at%206.50.07%20PM.jpg)

6. Define foreign key, primary key, and schema.

	- foreign key: used to link two tables together
	- primary key: assigned when object added to table- how the object is identified
	- schema: a representation of a database

7. Describe the relationship between a foreign key on one table and a primary key on another table.

	- a foreign key is a field in one table that refers to the primary key of another table

8. What are the parts of an HTTP response?

  - three parts: status line, header, body
  - the status line also contains three parts: status code, status phrase, http protocol


### Optional Questions

1. Name your five favorite ActiveRecord methods and describe what they do.  
	- ```.all```	selects all instances of the class
	- ```.where``` 	finds all instances that meet a given parameter
	- ```.order```	sorts instances DESC or ASC
	- ```.averge```	finds the average of a given numerical attribute
	- ```.sum```	finds the sum of a given numerical attribute

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
	- ```rake db:create```				creates the database
	- ```rake db:migrate```				creates tables based on migration
	- ```rake db:rollback```			steps back one migration

3. What two columns does `t.timestamps null: false` create in our database?
	- ```created_at```
	- ```updated_at```

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
	- a teacher `belongs_to` a school and a school `has_many` teachers

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
![teachers schools](https://cl.ly/0K1l0X2S3h38/Screen%20Shot%202018-07-07%20at%207.03.50%20PM.jpg)

6. Give an example of when you might want to store information besides ids on a join table.
	- not sure honestly

7. Describe and diagram the relationship between patients and doctors.
	- a doctor has many patients and a patient belongs to a doctor
	- one to many
	![doctor patients](https://cl.ly/2F3L0h2c0X2M/Screen%20Shot%202018-07-07%20at%207.09.50%20PM.jpg)

8. Describe and diagram the relationship between museums and original_paintings.
	- a museum has many original paintings and an original painting belongs to one museum
	- one to many
![museum painting](https://cl.ly/2e0V2s3l093E/Screen%20Shot%202018-07-07%20at%207.12.09%20PM.jpg)
	

9. What could you see in your code that would make you think you might want to create a partial?
	- i think about partials like modules- anything that is repeated could be stored in a partial

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
