## Week Four Recap

### Week 4 Questions

1. What is a cookie?

- small text files store on client computer
- created when you visit the site
- track movements, not personal data

2. What’s the difference between a session and a cookie?

- cookies and sessions are used to store information
- cookies are stored client-side
- sessions can be stored client side but also server side

3. What’s a flash and when do you want to use flashes?

- message presented to the user letting them know what actions did or did not take place

4. Why do people say “HTTP is stateless”?

- our web applications don’t recognize when two requests come from the same browser
- we use cookies to transfer state

5. What’s authentication? Explain.

- answers the question 'Who are you?'

6. What’s the difference between authentication and authorization?

- authentication- :Who are you?
- authorization- :Are you allowed to be here?

7. What’s a before filter?

- methods that are called before CRUD functionality
- a means to DRY source code and testing

8. How do we keep track of a user once they’ve logged in?

- sessions

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

- namespacing is used for organization
- nest resources if they can only exist by way of another resource
- nesting relies on two resources, namespacing is a single resource?

10. At a high level, what tools can you use to implement authorization? How would you use them?

- multiple controllers
- verify CRUD functionality using current_admin? and/or current_user? methods

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

- attribute that can have only one of a few different values
- integer
- model

12. What are some strategies you can use to keep your views DRY?

- use partials
- HTML5 page formatting, nav bars, font links in your layout/application.html.erb


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  

`array_of_hashes.sort_by { |hash| hash[:holiday][:name] }`

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?

- format the data using .to_i

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:

* I feel comfortable with the content presented this week
