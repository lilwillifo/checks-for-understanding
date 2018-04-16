### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
You'll set the flash as a hash in the controller eg flash[:success] = 'Successfully logged in'
Then in application.html.erb (or a nav etc)
<% flash.each do |name, msg| %>
<%= content_tag :div, msg, class: name %>
<% end %>
2. Where is cart information/temporary information usually stored?
session hash
3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
It is inefficient to be constantly adding/removing from the database. The information is temporary and we don't have a need to store this long term.
However I believe Amazon stores cart in their database. This way once I log out and log back in, my cart remains.
4. What is the purpose of the asset pipeline?
To reduce the number of request/responses in loading a site.
5. Why do we precompile our assets?
to make it slightly faster - less requests
6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```
They include the stylesheet, .js, and an image in the asset pipeline.
7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
It should include setup instructions, a description of what the repo does, and any known bugs/workarounds. Employers will likely read this!

8. What are the top four accessibility issues that we as developers should be aware of?
Did we cover this? I'm not sure what this is asking...

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
Callbacks are used in models.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

11. What is the difference between a scope and a class method?
class methods are called on the whole case

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
  cart['48'] = 4
  12b. How would you increase the quantity of item 29?  
  cart['29'] += 1
  12c. How would you find out how many items your user is thinking about purchasing?  
  If you don't care about quantity of each, then cart.keys.length, but if quantity matters then cart.values.sum

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  
polymorphism is using similar/mirroring methods in various places. Duck Typing is if it looks like a duck and it quacks like a duck, treat it like a duck! Active Record has active record associations, which aren't exactly arrays but similar enough that you can treat it as suck
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
string.split('(')[1].split(') ').join.split('-').join
### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
