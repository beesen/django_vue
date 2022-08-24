This tutorial assumes you have basic knowledge in Python, Django and VueJS
# Before we start
Lets see what dependencies we will need. Of course for the front end you will need to have
Node, npm/yarn and vue-cli installed. For the back end you will need Python and pip installed (I will be using Python 3.6) and also know how to use virtual environments. All these don’t take a lot of time to setup
and the internet is full of tutorials on how to install them.
Some truth from webdevelopersnotes.com
## Front End
1. Vue — The progressive framework for building user interfaces.
2. Vuetify — The material design framework for Vue
3. Axios — Promise based HTTP client for the browser and node.js
4. Sweet Alert 2 — For beautiful Alert messages
5. Vue Session — For storing user sessions (on the front end)
6. Vuex — For managing the state
## Back end
For the back end, you will need the following installed on your virtual environment.
1. Django (2.1 and above. I have not tested this with lower versions)
2. Django Rest Framework ( Django REST framework is a powerful and flexible toolkit for building Web
APIs)
3. Django CORS Headers — ( A Django App that adds CORS (Cross-Origin Resource Sharing) headers to
responses.)
4. Django Filter — ( Django-filter is a reusable Django application allowing users to declaratively add
dynamic QuerySet filtering from URL parameters.)
5. Django Rest Framework JWT — ( JSON Web Token Authentication support for Django REST Framework)
So, lets get started. I have to warn you though, I am using Windows 10. The process should be similar for
Unix based Operating Systems too.
## Setup the Back end
1. Create a virtual environment

Virtual environments are important but not compulsory. They come in handy if you have different projects
and each of them requires different versions of python packages (or even python versions).
### 2. Create the Project Directory
I will call mine **testlogin**. In it, I will have to directories: client and server.
cd into the **testlogin** directory.
### 3. Install Django
In this tutorial I will use Django 2.1. Therefore run the following command:
_pip install Django==2.1_
### 4. Create the Server
As I mentioned before, I will call my back end server
Creating the server:
```
django-admin startproject server
```
### 5. Install the back end packages
cd into the server folder and create a requirements.txt file. This file will help us to install the other packages
I mentioned before. You can copy mine.
The requirements.txt file:
```text
astroid==2.0.4
colorama==0.3.9
Django==2.1
django-cors-headers==2.2.0
django-filter==2.0.0
djangorestframework==3.8.2
djangorestframework-jwt==1.11.0
isort==4.3.4
lazy-object-proxy==1.3.1
mccabe==0.6.1
pycodestyle==2.4.0
PyJWT==1.6.4
pytz==2018.5
six==1.11.0
typed-ast==1.1.0
wrapt==1.10.11
```
Run _pip install -r requirements.txt_ to install all the packages.
After that update the requirements.txt file by running _pip freeze > requirements.txt_
### 6. Create the Movies App
We need to create the movies app. This app will be responsible for holding the details about the movie.
```python
django-admin startapp movies
```
That’s it for now, let us now set up the front end.
## Setup the Front End
Go back a step to the root of the **testlogin** folder and create the client app. We will be using a
vuetify/webpack template because it makes it easier to get started with vuetify.
```text
$ cd ..

$ vue init vuetifyjs/webpack client
$ Project name: client 
$ Project description: client
$ Author
$ Vue build: standalone
$ Install vue-router: yes
$ Use ESLint to lint your code: No
$ Setup unit tests: No
$ Setup e2e tests with HighWatch No
$ Use a-la-carte components No
$ Use custom theme No
$ Shoul we run 'npm install' for you? npm
vue-cli - Generated "client".
```
Note that I chose Yes for using vue-router. This will help us with navigation between the pages.
The next step is installing the front end dependencies. You will have to cd into the _client_ directory before
installing them.
```text
cd client
npm install --save axios sweetalert vue-session vuex
```
## Run!
Let’s run both the front end and back end and see if they work.
### Running the Client (front end)
cd into the client folder and run _npm run dev_
```text
cd code/testlogin/client
npm run dev
...
```
If you open your browser on localhost port 8080 you should see this:
The default page for Vuetify Apps.
You can play around with this page.
### Running the Server (back end)
cd into the **server** folder, activate your virtual environment and run python manage.py runserver
```text
python manage.py runserver
```
For now ignore the warnings of running migrations. We will deal with them in the second part.
Open your browser on localhost port 8000 and you should see this.
