# Getting Started
## Hello Rails I
Ruby on Rails is a web framework that makes it easy to build powerful web apps in a short amount of time.

Ruby on Rails is written in the Ruby programming language. If you are new to Ruby, we recommend you do this course first.

### Instructions

    1. Let's get started by making a Rails app for a personal website. We'll explain each  step in the next exercise. In the terminal, type:
            rails new MySite
    
    2. Then run: 
            bundle install
    
    3. Finally type:
            rails server

    4. View the Rails app in the browser by visiting http://localhost:8000. Then click Next to find out what these commands do.

## Hello Rails II
Nice work! In three commands, you built a working Rails app that displays the Rails default page. How does it work?
    
    1. The rails new command created a new Rails app named MySite. It generated a number of files and folders that we will use to build the app. In the Code Editor, click on the folder icon to see these files and folders. We'll see what these files and folders are for in the next exercises. The rails new command is the starting point of every Rails project.

    2. The bundle install command installed all the software packages needed by the new Rails app. These software packages are called gems and they are listed in the file Gemfile.

    3. The rails server command started the Rails development server so that we could preview the app in the browser by visiting http://localhost:8000. This development server is called WEBrick.

### Instructions
1. The new Rails app contains a number of files and folders. Click Next to find out how they work together.

## Controller
What happens when you visit http://localhost:8000 in the browser? Check out the diagram in the browser. [Read it](https://www.codecademy.com/articles/request-response-cycle-static)

    1. The browser makes a request for the URL http://localhost:8000.
    2. The request hits the Rails router in config/routes.rb. The router recognizes the URL and sends the request to the controller.
    3. The controller receives the request and processes it.
    4. The controller passes the request to the view.
    5. The view renders the page as HTML.
    6. The controller sends the HTML back to the browser for you to see.

This is called the request/response cycle. It's a useful way to see how a Rails app's files and folders fit together.

### Instructions
    1. Looking at the request/response cycle, we need three parts to build a Rails app: a controller, a route, and a view. Let's start here by creating a controller. In the terminal, type:
            rails generate controller Pages

    2. After rails generate finishes running, in the Code Editor, open app/controllers/pages_controller.rb. Within the class PagesController, add a method home:
       `class PagesController < ApplicationController 
            def home
            end
        end`
    
## Routes
Great! We created a new controller named Pages. How did we do this?

    1. The rails generate controller Pages command generated a new controller named Pages. This created a file named app/controllers/pages_controller.rb.

    2. Inside the new Pages controller, we added a method called home. Methods in Rails controllers are also referred to as controller actions, so here we added the home action to the Pages controller.

### Instructions
    
    1. Now that we have a controller, let's move on to the second part of the request/response cycle and create a route. Open config/routes.rb and underneath line 1,type: 
            get 'welcome' => 'pages#home'

