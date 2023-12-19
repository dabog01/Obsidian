--- 

Django is a python web framework which is going to allow us to write python code that is able to dynamically generate HTML and CSS allowing us to build a dynamic web applications.

--- 
## WorkFlow

1. Create software that's going to run on a web server
2. The clients, running in their web browser can make request to our web server
3. Our server is going to respond back with some sort of response

Thanks to... **HTTP** :3 
### HTTP

~~~
Request...

GET / HTTP/1.1
Host: www.example.com
...
~~~

#### HTTP Status code

| Status Code | Description |
| --- | --- |
| 200 | Ok |
| 301 | Moved Permanently |
| 403 | Forbidden |
| 404 | Not found|
| 500 | Internal server error |

~~~
Response...

GET / HTTP/1.1 200 
Content-Type: text.html
...
~~~

## Start with Django

**Instal Django**

~~~
>> pip3 install django
~~~

**Create a Django proyect**

~~~
>> django-admin startproyect <proyect_name>
~~~

**Run this web application**

~~~
>> python manage.py runserver
~~~

**NOTE : Every Django project generally consist of one or more Django application**

## Django app :)

1. Create a Django app 

 ~~~
 python manage.py startapp <app_name>
 ~~~

2. Go to **setting.py** on the <proyect_name> directory and add <app_name> to INSTALED_APPS = []

~~~
...
# Application definition
  
INSTALLED_APPS = [
    'hello',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.co...
~~~

3. Go to **views.py** on the <app_name> directory, and modify to something like this

~~~
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.

# means :
# form HTTP request that user made in order access our web server
# shoud be returns a HTTP response

def index(request):
    return HttpResponse("Hello, Word :)") 
~~~

To do that we're going to create a url.py file for this particular file

==**NOTE : We'll have each app contains its own urls.py file to control what URL's are available for that particular app**==

4. Create a urls.py file in <app_name> directory, must look something like this

~~~
from django.urls import path
from . import views

# list of all of the allowable URLs that can be accessed for this particular app
urlpatterns = [
    path("", views.index, name="index")
]
~~~

5. Go to urls.py file in <proyect_name> directory and modify it

~~~
"""
URL configuration for django_sample project.
The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/4.2/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
"""

from django.contrib import admin
from django.urls import path, include  

urlpatterns = [
    path('admin/', admin.site.urls),
    path('<app_name>', include("<app_name>.urls"))
]
~~~

6. Run the web application and redirect to the respective URL 

~~~
// terminal

>> python manage.py runserver
~~~

~~~
// http://127.0.0.1:8000/<app_name>
~~~

7. Create more routes

**Repit the 3th, 4th and 6th step creating a new responses and a new URL with a slight changes**

Go to **views.py** on the <app_name> directory, and modify to something like this

~~~
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.

# means :
# form HTTP request that user made in order access our web server
# shoud be returns a HTTP response

def index(request):
    return HttpResponse("Hello, Word :)") 

def alejandro(request):
    return HttpResponse("Hi, Alejandro :)") 
~~~

create a urls.py file in <app_name> directory, must look something like this

~~~
from django.urls import path
from . import views

# list of all of the allowable URLs that can be accessed for this particular app
urlpatterns = [
    path("", views.index, name="index"),
    path("alejandro", views.alejandro, name="alejandro")
]
~~~

run the web application and redirect to the respective URL 

~~~
// terminal

>> python manage.py runserver
~~~

~~~
// http://127.0.0.1:8000/<app_name>/<path_argument>
~~~

**NOTE : Up to this point it would seem that I need create a whole bunch of functions and URLs cause is what we need for each request...**

To solve this...

8. Create URL patterns that have placeholder 

Allows me parameterize the path via certain path converters.

Go to **views.py** on the <app_name> directory, and modify to something like this

~~~
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.

# means :
# form HTTP request that user made in order access our web server
# shoud be returns a HTTP response

def index(request):
    return HttpResponse("Hello, Word :)") 

def alejandro(request):
    return HttpResponse("Hi, Alejandro :)") 

def greet(request, name):
	return HttpsResponse(f"Hello {name.capitalize()}!")
~~~

create a urls.py file in <app_name> directory, must look something like this

~~~
from django.urls import path
from . import views

# list of all of the allowable URLs that can be accessed for this particular app
urlpatterns = [
    path("", views.index, name="index"),
    path("alejandro", views.alejandro, name="alejandro")
    path("<str:name>", views.greet, name="greet")
]
~~~

run the web application and redirect to the respective URL 

~~~
// check terminal

>> python manage.py runserver
~~~

~~~
// http://127.0.0.1:8000/<app_name>/<path_argument>
~~~

**But if if I have to include an entire HTML page just inside the HttpReponse() doble quotes??**

9. Following the exercise... now in stead of returning an HttpResponse() let me go ahead and render.

Go to **views.py** on the <app_name> directory, and modify to something like this

~~~
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.

# means :
# form HTTP request that user made in order access our web server
# shoud be returns a HTTP response

def index(request):
    return render(request, "hello/index.html") 

def alejandro(request):
    return HttpResponse("Hi, Alejandro :)") 

def greet(request, name):
	return render(request, "hello/greet.html"), {
		"name" : name.capitalize()
	}
~~~

To do this we will create a 'templates' directory and within it a <project_name> directory where you could create the greet and index html files...

==Right now you have to modify the files to it works==

This way...

~~~
// index.html

<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>
~~~

~~~
// greet.html

<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body>
        <h1>Hello, {{name}}!</h1>
    </body>
</html>
~~~

**Here is a lot of things happening in different places :p**

## Additional features ;)

Exist someone who modify the html of this page every year??

https://isitchristmas.com/

Now we can use the Python Logic!! Play with it :p

~~~
Experiment with python...

>> python

Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import datetime
>>> now  = datetime.datetime.now()
>>> now.year
2023
>>> now.month
6
>>> now.day
9
>>> now.hour
11
>>> now.month == 1, now.day == 1
(False, False)
>>> now.month == 1 & now.day == 1
False
>>>
~~~

Following up on the previous example

1. Start a new app name 'newyear''
2. Add the newyear app in the <proyect_name> directory and go to **setting.py** file in the INSTALLED_APPS = []
3. Add the URL for the newyear app in <proyect_name> directory and go to **urls.py**  file to add to the urlpatterns = []
4. Create a urls.py an the newyear app directory and add the route that loads your defined functions
5. Define a new function in the view.py an the newyear app directory and apply your logic

## Sessions

...

## Migrations 

Let's imagine that we already have been created a new Django project called **airline** and in the process we wanna create a new app for the fights management called flights, don't forget the settings.py and urls.py configurations in the airline directory...

~~~
## Go to flights directory and modify the models.py file to something like this

from django.db import models

# Create your models here.
""" Every model is going to be a python class """
# one model for each of main tables we care about storing information

class Flight(models.Model):
    origin = models.CharField(max_length=64)
    destination = models.CharField(max_length=64)
    duration = models.IntegerField()    
  
# first view migrations
""" Here some changes that i would like to apply to the database,
    Then I migrate them and tell Django to take those changes
    and apply them to the database
 """
~~~

take those instructions and apply them to the underline database

~~~
>> python manage.py makemigrations
~~~

And apply the migration to Django's database

~~~
>> python manage.py migrate
Try this too.. find the diferences :p
>> ls
~~~

### Shell

Django now gives us the ability to manipulate SQL just by using Python models

~~~
>> python manage.py shell
~~~

Write python commands to interact with these sorts of models 

![[Pasted image 20231002075356.png]]

**Abstactions layer!** https://en.wikipedia.org/wiki/Abstraction_layer

~~~~
// continuing with the migratons example

>>> from flights.models import Flight
>>> f = Flight(origin="New York", destination="london", duration="415")
>>> f.save()
>>> Flight.objects.all()
~~~~

~~~
PS C:\xampp\htdocs\samples\django\airline> python manage.py shell
Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from flights.models import Flight
>>> flights = Flight.objects.all()
>>> flights
<QuerySet [<Flight: 1 : New York to london>]>
>>> flight = flights.first()
>>> flight
<Flight: 1 : New York to london>
>>> flight.id
1
>>> flight.origin
'New York'
>>> flight.duration
415
>>> flight.delete()
(1, {'flights.Flight': 1})
~~~

### Foreign Keys

~~~
## Go to flights directory and modify the models.py file to something like this

from django.db import models

class Airport(models.Model):
    code = models.CharField(max_length=3)
    city = models.CharField(max_length=64)

    def __str__(self):
        return f"{self.city} ({self.code})"    
  
class Flight(models.Model):
    origin = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="departures")
    destination = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="arrivals")
    duration = models.IntegerField()    

	# cleaner way to seeing the name of a particular flight    
    def __str__(self):
        return f"{self.id} : {self.origin} to {self.destination}"
~~~

~~~
>> python manage.py makemigrations
~~~

~~~
>> python manage.py migrate
~~~

~~~
>>> python manage.py shell
Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from flights.models import *
>>> jfk = Airport(code="JFK", city="New York")
>>> jfk.save()
>>> lhr = Airport(code="LHR", city="London")
>>> lhr.save()
>>> cdg = Airport(code="CDG", city="Paris")
>>> cdg.save()
>>> nrt = Airport(code="NRT", city="Tokyo")
>>> nrt.save()
>>> f = Flight(origin=jfk, destination=lhr, duration=415)
>>> f.save()
>>> f
<Flight: 1 : New York (JFK) to London (LHR)>
>>> f.origin
<Airport: New York (JFK)>
>>> f.city
Traceback (most recent call last):
  File "<console>", line 1, in <module>
AttributeError: 'Flight' object has no attribute 'city'
>>> f.origin.city
'New York'
>>> f.origin.code
'JFK'
>>> lhr.arrivals.all()
<QuerySet [<Flight: 1 : New York (JFK) to London (LHR)>]>
~~~

how I give those results back to me... 

In the flight app directory create a new template directory and add these flies

~~~
// layout.html

<!DOCTYPE html>
<hmtl lang="en">
    <head>
        <title>Flights!</title>
    </head>
    <body>
        {% block body %}
        {% endblock %}
    </body>
</hmtl>
~~~

~~~
// index.html

{% extends "flights/layout.html" %}

{% block body %}
    <h1>Flights</h1>
    <ul>
        {% for flight in flights %}
            <li>Flight {{ flight.id }}: {{ flight.origin }} to {{flight.destination}} </li>
        {% endfor %}
    </ul>
{% endblock %}
~~~

Your view.py file must look like this

~~~
// view.py 

from django.shortcuts import render
from .models import Flight

# Create your views here.
def index(request):
    return render(request, "flights/index.html", {
        "flights": Flight.objects.all()
    })
~~~

The shell is too enoying!!!

## Django admin app

App just designed for the manipulation of these models

You remember at the airline directory a code line like these in the urls.py file?

~~~
path('admin/', admin.site.urls)
~~~

Let's get to it...

1. Create an administrative account inside of our Django web app

~~~
>> python manage.py createsuperuser
~~~

2. Modify the admin.py file on the flights directory

~~~
from django.contrib import admin
from .models import Flight, Airport

# Register your models here.
  
admin.site.register(Airport)
admin.site.register(Flight)
~~~

3. Go to the /admin URL and login with the superuser data and you must be able to interact with the underlying database via web interface


