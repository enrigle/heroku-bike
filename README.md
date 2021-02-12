# cambridgespark-webapp

Code for the web app built as part of this tutorial I wrote for Cambridge Spark: https://blog.cambridgespark.com/deploying-a-machine-learning-model-to-the-web-725688b851c7

#Can be deployed to Heroku. Example running here: https://bike-model.herokuapp.com/

# Structure of the program
webapp/
    ├── model/
    │   └── bike_model_xgboost.pkl
    ├── templates/
    │   └── main.html
    ├── requirements.txt
    ├── Procfile
    └── app.py   

# Local testing
To start up flask on your local machine, make sure you are in the webapp folder and run the command:

*flask run*

# Deployment
1. Sign up for a free Heroku account at: https://signup.heroku.com/signup/dc
2. Make sure you have git installed, to push your app to Heroku.
3. Install the Heroku CLI tool.

After that:
1. Inside the webapp folder, run the following to create a new repository.
*git init*

2. Authenticate with Heroku
*heroku login*
 2.1. Press any key to go to the browser
 2.2. Log in to the Heroku CLI, then a message will appear: *You can close this page and return to your CLI. It should now be logged in.*, and return to the terminal
 2.3. Two messages appear in the terminal:
    Logging in... done
    Logged in as name@gmail.com


3. Create a new Heroku app
*heroku create*

4. If you want to choose your own name, simply pass it as an argument. For example:
*heroku create bike-model*



 
