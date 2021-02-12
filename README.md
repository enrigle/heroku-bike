# heroku-app
Simple app to test heroku web app

# Structure of the app
* webapp/
*    ├── model/
*    │   └── bike_model_xgboost.pkl
*    ├── templates/
*    │   └── main.html
*    ├── requirements.txt
*    ├── Procfile
*    └── app.py   

# Create the model using a notebook
Check the *training_model.ipynb*, where xgboost model is saved.

# Local testing
To start up flask on your local machine, make sure you are in the webapp folder and run the command:
> flask run

# Deployment
1. Sign up for a free Heroku account at: https://signup.heroku.com/signup/dc
2. Make sure you have git installed, to push your app to Heroku.
3. Install the Heroku CLI tool.

# Git and heroku CLI:

1. Inside the webapp folder, run the following to create a new repository.
    *git init*

2. Authenticate with Heroku
    *heroku login*
    * 2.1. Press any key to go to the browser
    * 2.2. Log in to the Heroku CLI, then a message will appear: *You can close this page and return to your CLI. It should now be logged in.*, and return to the terminal
    * 2.3. Two messages appear in the terminal:
      *Logging in... done*
      *Logged in as name@gmail.com*
    *2.4. *heroku create bikes-model*

    Another way to create the Heroku web page is by going to the Heroku website:
    * 2.5. Create an app, i.e. with the **App name** *bikes-model*
    * 2.6. Choose a region: *Europe*
    * 2.7. Click create app    

3. Aditional files:
    * 3.1. **requirements.txt**: this tells Heroku which packages to install for your web app. It should look like this:
    >flask
    >pandas
    >gunicorn
    >xgboost

    * 3.2. **Procfile**: this tells Heroku what kind of app you are running and how to serve it to users. It is a single line and should look like this:
    > *web: gunicorn app:app*

4. Add files to repository:
In the webapp folder, use the following command to add all your web app's files to the git repository:
    > git add .*
    > git commit -m "First commit"*

5. Set the remote destination for pushing from git to Heroku:
This command makes it easier to push your local web app to Heroku, using git.
You should change bikes-model to whatever you named your Heroku app when you created it.
    > heroku git:remote -a bikes-model
    
    > terminal's result:
    
    > set git remote heroku to https://git.heroku.com/bikes-model.git*

7. Push your app to the web
    > *git push heroku master*
    
    > **terminal's result:**
    
    > *remote:        https://bikes-model.herokuapp.com/ deployed to Heroku*
    
    > *remote: Verifying deploy... done.*
    
    > *To https://git.heroku.com/bikes-model.git*
    
    > *[new branch]      master -> master*

8. Check out the deployed app
You can use the heroku open command to open your completed app in the web browser. 
https://bikes-model.herokuapp.com/
  
9. Close the app
There are 2 ways to remove the app:
    * 9.1. From the Heroku Web
    > Dashboard => Your App Name => Resources => Pencil icon=> Flip the switch => Confirm
    * 9.2. To completely stop your app you can scale the web dynos down to zero which effectively takes all your app http-processes offline.
    > $ heroku ps:scale web=0* 
        
**Reference**: Blog for the web app built as part of this tutorial from Cambridge Spark: https://blog.cambridgespark.com/deploying-a-machine-learning-model-to-the-web-725688b851c7
         
