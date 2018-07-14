## Week Three Recap

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?  

`rails new 'PROJECT NAME HERE' -T -d="postgresql" --skip-turbolinks --skip-spring`

2. What do Models generally inherit from in rails?  

- ApplicationRecord

3. What do Controllers generally inherit from in a rails project?  

- ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?  

- add the following to config/routes in your app: 
```ruby
resources :horses, only: [:show]
```

5. What rake task is useful when looking at routes, and what information does it give you?  

`rake routes` 
- command will print the following info to the terminal: the prefix (which is your
route helper), the HTTP method, the URI pattern, the controller location and the  
method within said controller.

6. What is an example of a route helper? When would you use them?  

`horse_path(horse)` 
- would be the route helper for the horse show page.  
You can use route helpers in your app to follow rails convention.  
They make our lives easier bc we don't have to type out entire URLs.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?  

- `_url` will return the `http://` portion along with the `_path`
- the `_path` returns only the URI not the protocol

8. What are strong params and why are they necessary?  

- strong params are complementary to a controller- using strong params adds security to the HTTP params object that comes in from a form

9. What role does `form_for` play in helping us create our forms?  

- a helper method to create HTML form elements 

10. How does `form_for` know where to submit the user's input?  

- Rails will check for you if the object has been saved yet. If it’s a new object, it will send the form to your #create action. 
If the object has been saved before, Rails recognizes that we’re editing an existing object and will send the form to your #update action instead. 

11. Create a form using a `form_for` helper to create a new `Horse`.   

```ruby 
form_for [@horse] do |f|
f.label :name 
f.text_field :name

f.label :breed
f.text_field :breed

f.label :owner
f.text_field :owner

f.submit
end
```

12. Why do we want to validate our models?
- data integrity, analysis integrity

13. What are the steps of the DNS lookup?
- Client -> Browser -> DNS 
- DNS Server aka Resolver will take the URL the client enters into the browser and do a search starting at the root
- Root will send the resolver to the TLD server based on the top level domain extension in the URL
- TLD server will send the resolver to the authoritative name server based on the domain name in the URL
- ANS will respond back to the resolver with the IP address
- All within nano seconds ;)


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
```ruby
class Horse 

def prance
"Look at me prancing!"
end

def move
prance
end

end
```
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?

- the level at which the information is nested

`furniture[:table][:height] => 3`
`furniture[:purchased] => true`

16. What is inheritance?
- enables new objects to take on properties of other preexisting objects

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week

