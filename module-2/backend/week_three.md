## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
  rails new whatever -T -d="postgresql" --skip-turbolinks --skip-spring
  ^^I had to look this up. I created a rails setup gist where I pull this from...

2. What do Models generally inherit from in rails?
  ApplicationRecord

3. What do Controllers generally inherit from in a rails project?
  ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
  resources :horses, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?
  rails routes (or rake routes) shows you the path helper, the controller action, and URI

6. What is an example of a route helper? When would you use them?
  new_horse_path, you could call this in a test when visiting a page, or redirect here in the controller

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
  url includes the domain name, path only includes after .com

8. What are strong params and why are they necessary?
  they are params that you allow a user to post. they live in a private method in a controller so that you can control what attributes a user is allowed to manipulate

9. What role does `form_for` play in helping us create our forms?
  it takes a resource as an argument and builds the method/path for the submit button. It directs where the info will be saved

10. How does `form_for` know where to submit the user's input?
  based on the instance variable(s) passed to it. it stores info in the index

11. Create a form using a `form_for` helper to create a new `Horse`.
  <%= form_for @horse do |f| %>
    <%= f.label :name %>
    <%= f.text_field :name %>
    <%= f.submit %>
  <% end %>

12. Why do we want to validate our models?
  we need at least one attribute for the model to make sense - there's no sense in having an resource with no attributes

13. What are the steps of the DNS lookup?
  the user inputs domain name (google.com) and its then sent to check local cache, and then various levels up the chain to find an instance of that domain name. it then returns the IP address and includes that in the HTTP request.


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
  self.prance
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  
furniture[purchased] = true
furniture[table][height] = 3

16. What is inheritance?
a module or superclass has methods that are passed down to classes. You can call all the methods of the superclass without having to explicitly define them again in your class.

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
