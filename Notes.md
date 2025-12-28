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
- __init__.py : Blanck file: to create the folder as a python package
- admin.py : Register your models (any table you create in models.py, regisger in admin.py) (noet in urls: admin is default urlpatern)
		-- http://127.0.0.1:8000/admin (create user name)
		-- could be used with admin interface
- apps.py       -- Settings specific to our application
- models.py : Database(sql lite available by default): We need to get all the tables created here (store application data models)
- tests.py : Create your test case (unit testing done using by this), test function to test our code.
- views.py : Has functions that handles our request and return the responses.
- migration folder: Should contain __init__.py to make this as a package
	-- Stores database specific information related to models.

Note: Imp file:  Models.py and views.py

Testing types:
Unit testing
Integration testing
System testing


1. 
Add the installed apps in the projects setttings.py (already present 
INSTALLED_APPS = [

2. Views: Write funcitons

2. . Define the function for the URL in application
Eg: 
from Django.http import HttpResponse
def display(reqest):
  s= '<h1>Hello Students </h>'
  return HttpResponse(s)

3. Define the URL pattern for function in : urls.py
- import the funciton first and then define

Note: So flow (User sends-> Request -> Url.py(pattern) -> Calls function in views.py)

Views: MVT architecture (V: Views.py: logics written)
View has the business logic (i.e response based on business logic)
Two types of vies: 
1. Function based view (FBVs) (current eg, which we did)
2. Class based views (CBVs) 

Assignment:
1. Create a new project secondproject: 
2. Create an application in secondproject (as firstapp)
3. Add app in settings.py
4. define function in views.py (TIME_INFO) (eg2: based on time, good morning, eveing,night)
5. define in url pattern (/time)

Day: 5
Single application with multiple views:
1. create project
2. Create an application (jobs)
3. Add application in settings.py
4. declare multiple fuctions in views.py
	- Pune job
	- hydrabad job 
5. define url patterns in urls.py (for all functions)
6. Start the server

Note when we have multiple apps in url patten we import views of each app
but in python due to overloading (last menthod only considered)

Solution: 
1. Use aliasing
Eg: 
from firstapp import views as v1
from second import views as v2
use path('vish1/',v1.<functionName>)

2. Call funcitons directly by importing the functions
from firstapp import views import <functionName>
from second import views import <functionName>
use path('vish1/',<functionName>)


Reusable apps: i.e use these apps in 2nd projects 
i.e 5 apps having 50 funcitons , but urls.py we need to manually write

So for each app, create its own urls.py

# Defining URLs at application reather than project level for reusability: 
- Define urls.py: at application level
- Link this application lvel urls.py file to project level urls.py by using include function.

Go to views.py: define few functions:

def first_views(request):
	retun HtppResponse('<h1></h1>')

def first_views(request):
	retun HtppResponse('<h1></h1>')

Create a separate file urls.py in the applicaion 
Create url pattern similar to project one, and in project one include the below
    path('firstapp/', include('firstapp.urls')),  # 👈 include firstapp URLs

Way to access: http://127.0.0.1:8000/firstapp/first/
i.e <>/<appName><urlPatternInApp>


Use of this:
When you coupy pase the existing app to another project, no need to remap the urls



Django Template & Static Files: 
Views.py: write only python code (use pure python logic)
Template: Separate the html code from the views file and crate in a template files.

Not recommended to write htm in views.py: 
- Code mixing
- No separation of code (HTM we could have separate developer)
- No reusability
- Write templates at project level only, use these in multiple applications.

=============
Pathlibs: module
path: class

zipfile: module
ZipFile: Class

pathlibg module provides various classes repsenting filesystem paths based on diff operating systems.

In settings.py
Base_Dir =Path(__file__).resolve().parent.parent
Gives the project folder name
============

=======================
Day 7: Templates
MVC Patter: Controller in .net
MVT Pattern: Django (Model(database), V: Business logic in python file, T: Template(presentation layer)

1. Create project
2. create application 
3. add application name in settings.py
4. create a folder: templates inside main folder(project)
   in that template folder, create separate folders as per your applications (application specific templates)
5. Settings.py: Templates -> DIRS -> Give the path of the folder
TEMPLATES_DIRS = BASE_DIR / 'templates'

6. Create html file inside testapp folder.
	Eg: Wish.html
7. Define function based view inside views.py
To send respose of html page as resonse
views.py
8. Create a url patten at project level
9. Start the server
==============================================================================
Models: Creating tables:
1. Create table in models.py
models.py
----------------
class Employee(models.Model):
    eno = models.IntegerField()
    ename = models.CharField(max_length=30)
    esal = models.FloatField()
    eaddr = models.CharField(max_length=30)

i) py manage.py makemigrations	

ii) How to see the corresponding SQL code of migrations: (i.e create table statement)
D:\DJANGO_12DEC_730PM\modelproject>py manage.py sqlmigrate testapp 0001

iii) How to execute generated SQL code:
After generating SQL code, we have to execute that SQL code to create table in database. 
For this we have to use 'migrate' command.
py manage.py migrate


2. Register in admin.py to view from admin panel:
We have to register model class admin.py file

admin.py
--------------
from testapp.models import Employee
admin.site.register(Employee)


3. 
Creation of super user to login to admin interface

We can create super user by using the command:
py manage.py createsuperuser
http://127.0.0.1:8000/admin/


Q.Difference between makemigrations and migrate?

'makemigrations' is responsible to generate SQL code for python model class 
'migrate' is responsible to execute the SQL code so that tables will be created in the database.

==============================================================================
Note:
==============================================================================
Database Configuration:
-----------------------
-->If we want to use default DB sqlite3, we are not required to do any configuration.
-->The default sqlite3 configurations in settings.py file are declared as:
	
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

Database connection with MySql
--------------------------------------------------
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'djangodb',
		'USER': 'root',
		'PASSWORD': 'root',
		'HOST': 'localhost',
		'PORT': 3306
    }
}

Database connection with Oracle
--------------------------------------------------
>>> select * from global_name;
----------------------------------------------
ORCL

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.oracle',
        'NAME': 'ORCL',
		'USER': 'scott',
		'PASSWORD': 'tiger',
		'HOST': 'localhost',
		'PORT': 1521
    }
}

-->If we dont want to use sqlite3 DB then we have to configure our own DB with the parameters.
			1).ENGINE:Name of the DB engine
			2).NAME:Database name
			3).USER:Database login user name
			4).PASSWORD:Database login pasword
			5).HOST:The machine on which DB server is running
			6).PORT:The port number on which Db server is running
Note:	Most of the times HOST and PORT are optional.

How to check Django Database Connection:
------------------------------------------------------------------
-->We can check whether django database configurations are properly configured or not by using the command from the shell.
		D:\DJANGO_12DEC_730PM\maheshnewsproject>py manage.py shell
		>>> from django.db import connection
		>>> c = connection.cursor()		
-->If we are not getting any error our database configurations are proper.
