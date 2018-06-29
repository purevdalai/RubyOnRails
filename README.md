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
    


## Controller
What did we just do?
    1. The rails generate model command created a new model named Message. In doing so, Rails created two files:

        * a model file in app/models/message.rb. The model represents a table in the database.

        * a migration file in db/migrate/. Migrations are a way to update the database
    
    2. Open the migration file in db/migrate/. The migration file contains a few things:

        * The change method tells Rails what change to make to the database. Here it uses the create_table method to create a new table in the database for storing messages.

        * Inside create_table, we added t.text :content. This will create a text column called content in the messages tables.

        * The final line t.timestamps is a Rails command that creates two more columns in the messages table called created_at and updated_at. These columns are automatically set when a message is created and updated
    
    3. The rake db:migrate command updates the database with the new messages data model.
    
    4. Finally the rake db:seed command seeds the database with sample data from db/seeds.rb.

### Instructions

    1. Now that we have a model, let's move on to the second and third parts of the request/response cycle and create a controller and a route. Generate a controller named Messages.

    2. In the routes file, create a route that maps the URL /messages to the Messages controller's index action.

    3. Then in the Messages controller (app/controllers/messages_controller.rb), add an index action:
        def index 
            @messages = Message.all 
        end
    
    