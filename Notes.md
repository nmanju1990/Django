All application: 
Presentation layer : Front end (HTML, CSS, JS, Jquery, bootstrap)
Business layer: Logic
Data layer


Web Application: 
1. Front end (HTML, CSS, JS, Jquery, bootstrap)

2. Backend: 
- Language(python)
- Framework(Djanog/Flask/Pyramid)
- Database (sqllite3,mongo db,mysql, oracle)


Developmont models
Software development cycle
Agile
Devops
RAD(rapid application development): Django support
MVT: Model , View, Template : Django
MVC: .Net (Model view controller)
DSF(Django Software Foundation )

====================================================================
Django: (Fast, Fully loaded, security, scalability, versatile) 
- Webapplicaiton framework 
- DRY(Don't repeat yourself)
- Provides (RAD(Rapid application development) facility
- Base don MVT(model, view, Tempalte)


MVT: (In Django)
Collecton of all html: Template: (presentation layer)
Views.py: Business logic (Business layer): In python
Database: Is called model


Django Installation: 
1. Python install and check version: 
python --version


2. 
https://www.djangoproject.com/download/
py -m pip install Django==6.0
pip install Django==5.1

py -m Django --version

In a Django project, you have multiple application (Eg: University project,
application: Students registration, teacher registration)

Django project: is a collection of application and config (web application)

mkdir DJANGO_11Dec
cd <>

To create Django project: 
django-admin startproject  firstproject or 
py -m- django startproject  firstproject

See stucturue: 
tree /f

Files:
A. Manage.py

B. 
1. __init__.py: Blanck file: to create the folder as a python package
2. Settings.py: Settings for project (Eg: templstes / version, database etc) 
	installed apps, middleware, database

3. urls.py: For diff url patterns 
4. Wsgi.py: 
	webserverver gateway intefae 
	- ( to develop application in productions
5. asgi.py: 
	asgi: Asynchronous server gateway Inteface: 

6. manage.py: 
	- Most commonly used script (to run development server)
	- Interact with django
	- run development server, testcase 	

Note: WSGI.py and asgi.py: Used during deployment

====================
Ch: 3
1 project: Multiple applicaiton inside that
2. TO run a project: Command : Move to manage.py location and run
cd firstproject
- py manage.py runserver (note: runserver: is a command line argument) : 
http://127.0.0.1:8000
http://127.0.0.1 (Server)
8000 (Port No) : Every applicaiton running in diff applicaion is called port no (i.e differnt class in a college)
	Default port no, could be changed.


Any web applicaiton:
User sends request and gets back response
In django: it goes to urls.py

Web server: (Created by Djanog in our case)
provides environment to run web applicaiton: 
receive reqests from user, and forward to web component based on url pattern & provide response to end user.
Sqllite3: default database

Creating first web application (in our project): 
Ctl+ C : Stops server

Creating application:

py manage.py startapp firstapp  (check the structure inside)
Creates below files:
- migration folder
- __init__.py : Blanck file: to create the folder as a python package
- admin.py : Register your models (any table you create in models.py, regisger in admin.py) (noet in urls: admin is default urlpatern)
		-- http://127.0.0.1:8000/admin (create user name)
		-- could be used with admin interface
- apps.py       -- Settings specific to our application
- models.py : Database(sql lite available by default): We need to get all the tables created here (store application data models)
- tests.py : Create your test case (unit testing done using by this), test function to test our code.
- views.py : Has functions that handles our request and return the responses.

Testing types:
Unit testing
Integration testing
