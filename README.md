# Franks Ruby Stuff
---

Here is where I am going to gradually tweak all the stuff that 
goes along with setting up Rails. And I know that there are a
million of these but having my own should help me understand it
better and may even one day help me explain it better. 

## Starting From Scratch: Request-Response Cycle for Static Apps

This basically means setting up all the Router/Controller/Viewer 
stuff(?). 

From what I understamd: 

 + Router: Handles requests and points them to correct requests
 + Controller: connects the Viewer to the request 
 + Viewer: This is all of the plain HTML/CSS

### Starting a new project


```
my@shit:  ~/$ rails new MyNewApp
my@shit:  ~/$ bundle install
```


### Example Controller and Action setup

```
my@shit:  ~/$ rails generate controller pages
```

Then open `apps/controllers/pages_controller.rb` and add 
the methods you need. In this case we will add `home`. 

```
class PagesController < ApplicationController 
  
    # Here is the method that we created 
    #
    # vvv
  def home
  end
    # ^^^

end
```

Methods in Rails are also called actions, so this is the 
`home` action. 

### Example Route setup

This time we open `config/routes.rb` and add our route. In this 
case the route we are going to add is to `pages#home` from `welcome`
in the form of a hash. 

The new line in `config/routes.rb` will look like this: 
```
get 'welcome' => 'pages#home'
```

Basically what this is doing is saying "If I recieve a request to the 
page 'welcome' (more accurately: example.com/welcome) then use  
controller 'pages' >> action 'home' to direct to the correct page. 

### Example View setup

Here we are going to actually make the page that will be viewed by the 
peoson calling the site. Here we are going to make the page under
`app/views/pages/home.html.erb` (.erb = Embedded RuBy). This is the 
code that will be viewed when people request 'welcome'. 
```
<div class="main">
  <div class="container">
    <h1>Hello my name is __</h1>
    <p>I make Rails apps.</p>
  </div>
</div>
```
Feel free to add the other `<doctype>, <header>, <body>` tags. 

This will reference the CSS in `app/assets/stylesheets/pages.css.scss`. 

### What We just did!(?)!

So far what we have done is:

 + Initialize a new Rails project directory
 + Create a custom controller and action 
 + Create a router that will _use_ that controller and action
 + Create a view to complete the communication between the 
request and the final product. 

This is great progress, but this is just the beginning! After this we get 
into more of the backend part of Rails! Databases!


## Starting From Scratch: Request-Response Cycle for Static Apps


