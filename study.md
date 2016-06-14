# Rails as an API Study

Use your favorite search engine and the provided readings to research and answer
the following questions (no prior knowledge is expected).

In your answers, be sure to cite any relevant sources you consulted in your
search. We ask you to write answers in your own words in order to see how you
process what you've read. Please do not answer with direct quotes from source
material. Instead, digest what you've read and repeat it in your own voice.

Please note:

-   Many of the readings will mention the "view" layer. We won't be covering the
    view layer in this program.
-   We'll use our [rails-api-template](/ga-wdi-boston/rails-api-template)
    repository as the basis for our rails applications.
    This template excludes the "view" layer.

## Required Readings

-   [Starting Ruby on Rails: What I Wish I Knew | BetterExplained](http://betterexplained.com/articles/starting-ruby-on-rails-what-i-wish-i-knew/)
-   [Intermediate Rails: Understanding Models, Views and Controllers | BetterExplained](http://betterexplained.com/articles/intermediate-rails-understanding-models-views-and-controllers/)
-   [Getting Started with Rails — Ruby on Rails Guides](http://guides.rubyonrails.org/getting_started.html)
-   [The Rails Command Line — Ruby on Rails Guides](http://guides.rubyonrails.org/command_line.html)
-   [Rails Routing from the Outside In — Ruby on Rails Guides](http://guides.rubyonrails.org/routing.html)
-   [Action Controller Overview — Ruby on Rails Guides](http://guides.rubyonrails.org/action_controller_overview.html)

## Define Model Responsiblities

In your own words, define what the responsibilities of the model layer are in
Rails.

```md
The model layer is the background processes. They are Ruby classes that interact with the database to perform logic tests, authentication, and other calculations. The model layer is the slave to the controller
```

## Define Controller Responsiblities

In your own words, define what the responsibilities of the controller layer are
in Rails.

```md
The controller is the middle-man: when there is a request, the controller is the master to the model but slave to the dispatcher/browser requests then it responds by returning the product of the request back to the browser.  The maniplulation of the browser is also affected by the view and what the controller passes to view then effects what the controller returns to the browser.

The controller is the translator / commander that tells the model what needs to get done and waits for the result to return back. Data parsing happens here.

-handles sessions, logins, authorization, filters etc
-default actions

```

## Define Router Responsiblities

In your own words, define what the router does in Rails.

```md
Router responsibilities include finding the information that you request by parsing the input from the url and translating that into an appropriate action for the controller.  It also can generate urls and paths.

-incoming request (in form url + "get"/other method words)
-router reads the request and matches it to a controller ation
  -sends to appropriate controller with input parameters based on url request
-returns instance or whatever associated action was expected from controller.

Router with METHOD(destroy, read, update) on RESOURCE(games/) for instance with PARAMETER(games/15 where 15 is the id:)

```

## The Request-Response Cycle in Rails

Starting with a client making a GET request to a particular URL, describe how
the parts of Rails interact to produce and send a response.

```md
-Client makes get request in form og GET photos/15
-router receives request and translates it to send to controller
    apply method GET to resource 'photos' passing parameter 15
-calls photos controller, passes parameter 15.
-controller tells model to do behind the scenes work
    authentication, logic, retrieval
-model returns information to controller
-controller bosses view around to adjust view in browser
-all model + view data send back to the browser for manipulation / resutls
```
