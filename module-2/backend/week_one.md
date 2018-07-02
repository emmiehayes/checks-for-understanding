## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.
## Week One - Module 2 Recap

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
    - GET: reads/retrieves a resource
    - POST: creates a resource
    - PUT: updates a resource
    - PATCH: updates single piece of a resource
    - DELETE: deletes a resource

2. What is Sinatra?
    - web framework
    - has DSL

3. What is MVC?
    - design pattern for web applications
    - stands for Model, View, Controller
    - Models handle business logic and interact with the database
    - Views handle presentation logic, .erb files written in html and ruby
    - Controllers handle the application logic, interacts with the models and views

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
    - because we want to make ReSTful routes using CRUD, it's the most understood architecture

5. What types of variables are accessible in our view templates without explicitly passing them?
    - instance

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    erb :index
  end
  ```

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
    locals: (name = "Mr. Ed")
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
    - see code block

8. What's the purpose of ERB?
    - ERB means embedded ruby
    - .erb files can use ruby and html together

9. Why do I need a development AND test database?
    - so that when you are manipulating the data for testing purposes you are not risking the integrity of the dev database

10. What is CRUD and why is it important?
    - CRUD stands for Create, Read, Update, Destroy
    - models should have all four CRUD functionalities

11. What does HTTP stand for?
    - hypertext transfer protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
    - render to screen using ```<%= %>``` don't render to screen ```<% %>```

13. What's an ORM? What does it do?
    - ORM stands for Object Relational Mapper
    - ORMs are used to create ruby objects from a row in a database

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
    - ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
    - GET       /restaurants                         (render) shows list of all restaurants

    - GET       /restaurants/:id                     (render) shows a single restaurant based on the id

    - GET       /restaurants/new                     (render) shows form to create new restaurant

    - POST      /restaurants/:id                     (redirect) create a new restaurant

    - GET       /restaurants/:id/edit                (render) shows form to edit a single restaurant

    - PUT       /restaurants/:id                     (redirect) update a restaurant

    - DELETE    /restaurants/:id                     (redirect) delete a restaurant from the database

16. What's a migration?
    - builds table
    - generates schema

17. When you create a migration, does it automatically modify your database?
    - you will need to run rake:db migrate in the terminal before you can modify the database

18. How does a model relate to a database?
    - the model is how we query the database

19. What is the difference between `#new` and `#create`?
    - create includes new and save
    - if you only call .new you will need to call Class.save as well

### Review Questions:  
20. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
```
CSV.foreach('./data/film.csv', headers: true, header_converters: :symbol) do |film|
  Film.create(id:film[:id],title:film[:title], description:film[:description])
 ```   
21. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?
```
activities[:hiking][:supplies] << 'granola bar'
```

22. What are the 4 Principles of OOP? Give a one sentence explanation of each.
    - i don't believe we have actually learned this but here is what i learned just now
    - Encapsulation: restrict access
    - Data Abstraction: reduce code complexity
    - Polymorphism: enable separation of concerns
    - Inheritance: one object or class can inherit attributes from another

### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
