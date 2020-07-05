[![Forks][forks-shield]][forks-url]

[![Stargazers][stars-shield]][stars-url]

[![Issues][issues-shield]][issues-url]

[![LinkedIn][linkedin-shield]][linkedin-url]
# Deployment-Machine-Learning-Web-app-Heroku

### Why Deploy Machine Learning Models?

The deployment of machine learning models is the process of making models available in production where web applications, enterprise software and APIs can consume the trained model by providing new data points and generating predictions.Normally machine learning models are built so that they can be used to predict an outcome (binary value i.e. 1 or 0 for Classification, continuous values for Regression, labels for Clustering etc. 

There are two broad ways of generating predictions 
(i) predict by batch; 
(ii) predict in real-time ( we will see how to deploy a machine learning model to predict in real-time )

### Tasks

1) Train and validate models and develop a machine learning pipeline for deployment.
2) Build a basic HTML front-end with an input form for independent variables (age, sex, bmi, children, smoker, region).
3) Build a back-end of the web application using a Flask Framework.
4) Deploy the web app on Heroku. Once deployed, it will become publicly available and can be accessed via Web URL.

### Tools we will use in this?

You must have Pycaret(for Machine Leraning Model) and Flask (for API) installed.

##### PyCaret

PyCaret is an open source, low-code machine learning library in Python to train and deploy machine learning pipelines and models in production. PyCaret can be installed easily using pip.

#### for Jupyter notebook on your local computer
> pip install pycaret

#### for azure notebooks and google colab

> !pip install pycaret


#### Flask
Flask is a framework that allows you to build web applications. A web application can be a commercial website, a blog, e-commerce system, or an application that generates predictions from data provided in real-time using trained models. If you don’t have Flask installed, you can use pip to install it.

#### install flask
> pip install Flask


#### Heroku

Heroku is a platform as a service (PaaS) that enables the deployment of web apps based on a managed container system, with integrated data services and a powerful ecosystem. In simple words, this will allow you to take the application from your local machine to the cloud so that anybody can access it using a Web URL. In this tutorial we have chosen Heroku for deployment as it provides free resource hours when you sign up for new account.

#### Project Structure

This project has four major parts :

> requirements.txt- Itis a text file containing the names of the python packages required to execute the application. If these packages are not installed in the environment application is running, it will fail.

> model.py - This contains code fot our Machine Learning model to predict Insurance by collecting (age, sex, bmi, children, smoker, region)

> app.py - This contains Flask APIs that receives (age, sex, bmi, children, smoker, region) details through GUI or API calls, computes the precited value based on our model and returns it.

> request.py - This uses requests module to call APIs already defined in app.py and dispalys the returned value.

> templates - This folder contains the HTML template to allow user to enter employee detail and displays the predicted Insurance. 

Running the project Ensure that you are in the project home directory. Create the machine learning model by running below command

> python model.py This would create a serialized version of our model into a file model.pkl

Run app.py using below command to start Flask API

> python app.py

By default, flask will run on port 5000.

Navigate to URL http://localhost:5000
You should be able to view the homepage as below : alt text

Enter valid numerical values in all 6 input boxes and hit Predict.

If everything goes well, you should be able to see the predcited salary vaule on the HTML page! alt text

You can also send direct POST requests to FLask API using Python's inbuilt request module Run the beow command to send the request with some pre-popuated values -
python request.py
