## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
GET: read POST: create PUT/PATCH: edit (put is a full edit, patch only changes one part of a resource) DELETE: deletes a resource
2. What is Sinatra?
a lightweight Framework - DSL
4. What is MVC?
Model, View, and Controller
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
to be RESTful
6. What types of variables are accessible in our view templates without explicitly passing them?
instance
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
```ruby
get '/horses' do
  @count = 1
  @name = "Mr. Ed"
  erb :index
end
```
9. What's the purpose of ERB?
to use ruby and HTML to build a dynamic template for what the user sees
10. Why do I need a development AND test database?
so you can test small cases, edge cases, and so your tests don't take forever and you don't dirty your real database!
11. What is CRUD and why is it important?
CREATE, READ, UPDATE, DELETE. This is what every(most) resource should have the functionality to do
12. What does HTTP stand for?
Hypertext transfer protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
<%= %> returns the value of ruby code <% %> does not, its used for ruby logic within erb
14. What's an ORM?
object relational map - use object oriented language (ie Ruby) to wrap about relational database
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
Active Record
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
Get '/restaurants' is for read functionality on index page
Get '/restaurants/new' is for read functionality on the create a new restaurant page
Post '/restaurants' is for create functionality
GET '/restaurants/:id' is to visit an individual restaurant page
GET '/restaurants/:id/edit' is to visit the edit form page for a restaurant
put '/restaurants/:id' is to edit an individual restaurant
delete '/restaurants:id' is to delete a restaurant
17. What's a migration?
A list of instructions to build a table in your database
18. When you create a migration, does it automatically modify your database?
no, you need to run rake db:migrate
19. How does a model relate to a database?
a model is a ruby object that represents one row of a table in db and has class methods to hold logic
20. What is the difference between `#new` and `#create`?
new makes the row, but create makes the row AND saves it to the database.

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?
```ruby
CSV.foreach('films.csv', headers: true, header_converters: :symbol) do |row|
  Item.create(id: row[:id],
              title: row[:title],
              description: row[:description],
              )
end
```
22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?
```ruby
activities[:hiking][:supplies]  << 'granola bar'
```
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
Encapsulation - restricting access for attr_readers and attr_writers
Abstraction -
Inheritance - importance of superclasses and modules
Polymorphism - multiple methods with the same name but slightly different functionality



### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
