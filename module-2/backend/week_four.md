## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
Small bit of information stored about a user during a given session that live on client side and helps to make HTTP stateful
2. What’s the difference between a session and a cookie?
typically, the server has several sessions. Rails stores sessions on client side by default. session and cookies are both accessed as a hash in rails.
3. What’s a flash and when do you want to use flashes?
flash is a notice that appears once when a page loads after a user action (ex. 'message deleted!' 'successfully logged out!' 'that username is taken')
4. Why do people say “HTTP is stateless”?
without sessions or cookies, each request and response is independent of each other. there is no memory or 'current state'
5. What’s authentication? Explain.
logging in - making sure that a user is who they say they are. typically with a username and password.
6. What’s the difference between authentication and authorization?
authentication is verifying WHO you are, authorization is verifying what you can and cannot see - access rights.
7. What’s a before filter?
in a controller, you can set a before_action to call a private method (ex require_admin or require_login) to ensure proper authorization
8. How do we keep track of a user once they’ve logged in?
session id and the current_user
9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
if you want to change the URI to signify different access (eg admin/categories)
Nesting resources is for object relations - eg if an item belongs to a merchant, items would be nested under merchants
10. At a high level, what tools can you use to implement authorization? How would you use them?
namespacing to change the URI to admin/...
before action requiring admin login, you can have a mid layer base controller between application controller and the admin controllers to store common methods
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
enum is an active record method that lets you assign an alias to a numeric attribute. Roles for auth are stored as integers, but then assigned an alias for easier/more clear recall. The enum call lives in the model
12. What are some strategies you can use to keep your views DRY?
break out partials and never call a model directly in the view. There should be


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  
```ruby
array.map do |hash|
  hash[:holiday][:name]
end.sort
```  

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?
data.split('$')[-1].to_i


### Self Assessment:
Choose One:
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel comfortable with the content presented this week
