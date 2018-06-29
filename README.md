# Saving Data
## Request/Response Cycle
So far we've built a Rails app containing a static page. To do this, we used a controller, a route, and a view. The request/response cycle summarizes how these three parts work together.

However, a Rails app with static pages looks the same for all users. How can we create apps that save information? We do this with a database. Here's how a database fits into the request-response cycle. Check out the diagram in the browser.[read it](https://www.codecademy.com/articles/request-response-cycle-dynamic)

    1. When you type http://localhost:8000/welcome, the browser makes a request for the URL /welcome.
    2. The request hits the Rails router.
    3. The router maps the URL to a controller action to handle the request.
    4. The controller action recieves the request, and asks the model to fetch data from the database.
    5. The model returns data to the controller action.
    6. The controller action passes the data on to the view.
    7. The view renders the page as HTML.
    8. The controller sends the HTML back to the browser.

### Instructions
    1. Let's see how to incorporate a database by building a Rails app for a messaging service. Create a new Rails app named MessengerApp using the rails new command.

    2. Install the gems in Gemfile.
    3. Run the local server to view the app at http://localhost:8000.


## Model

Great! You created a new Rails app named MessengerApp.

Looking at the request/response cycle, we need four parts to build a Rails app - a model, a route, a controller, and a view.

Let's start here by creating a model.

### Instructions
    1. In the terminal, generate a new model named Message :
        rails generate model Message
    
    2. Open the migration file in db/migrate/ for the messages table. The name of the migration file starts with the timestamp of when it was created. Inside the change method, add this line as line 4:
        t.text :content
    
    3. Then in the terminal, run:
        rake db:migrate

    4. Finally, run:
        rake db:seed
    
