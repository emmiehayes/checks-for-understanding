### Week 5 Questions
1. How do we make flash messages display on a page?
	- in the controller you include something like:
	   flash[:alert] = "Invalid account password, must be 1,008 characters long."
	- in the application html file we paste a code snippet similar to this:
    <% flash.each do |type, message| %>
      <%= content_tag :div, message.html_safe, class: type %>
    <% end %>

2. Where is cart information/temporary information usually stored?

	- a session

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?

	- the cart is temporary so if you are not running analysis on the items in the cart i 	don't see a need to store in a db for long term

4. What is the purpose of the asset pipeline?

	- provides a framework to concatenate and minify or compress JavaScript and CSS assets

5. Why do we precompile our assets?

	- so that the assets don't break when we run production locally

6. What do each of the following tags do?

	- they are all links to include front-end assets

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

	- project title and motivation for build
	- tech stack used
	- installation details
	- benefit to a good readme is more people are likely to clone and explore your repo if they know what is going on.

8. What are the top four accessibility issues that we as developers should be aware of?

	- Visual
	- Mobility
	- Cognition
	- Hearing

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
	- model callback
	- model

10. Given the following object, how would we create a scope for all users who are active?

`User.create(name: "Happy", active: true)`

- `scope :active, -> { where(active: true) }`

11. What is the difference between a scope and a class method?

	- apparently they are basically the same, scope is just less error prone?


### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?
	`cart['48'] = 4`

  12b. How would you increase the quantity of item 29?  
 	`cart['29'] + 1`

  12c. How would you find out how many items your user is thinking about purchasing?
  	`cart.values.sum`

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  

	- polymorphism is the ability to process objects differently depending on their data type or class
	- duck-typing: if an object walks like a duck and talks like a duck, then the Ruby interpreter is happy to treat it as if it were a duck.


14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  

	- user the number_to_phone helper?

### Self Assessment:
* I was able to answer most questions independently, but utilized outside resources for a few

* I feel comfortable with the content presented this week
