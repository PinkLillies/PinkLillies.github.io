# Django - Basics

You can install django with this command

`pip3 install Django`


## Create a new project

To create a new project:

```django
django-admin startproject lecture3
```

_(note: you need to be in the folder that contains django-admin.exe)_

then go to the directory and open Visual Studio Code:

`cd lecture3`

`code .`


## Run your website

you can now run your server and you will land on the default page

```django
python manage.py runserver
```

## Create a new app

Every new project needs to have at least one app. To create a new app called flights:

```django
python manage.py startapp hello
```


## Set up your new app properly

### step 1:

First thing you need to do after you create your first app is to edit **settings.py** in **lecture3 folder**

Under INSTALLED_APPS, add:

`'hello',`

### step 2:

Then we need to edit **views.py** under **hello folder**:

```
from django.http.response import HttpResponse
from django.shortcuts import render

# Create your views here.
def index(request):
    return HttpResponse("Hello world")
```

_we defined a function called index that will return hello world


### step 3:

Create a new file under **hello folder** called **urls.py** and add:


```
from django.urls import path

from . import views

urlpatterns = [
    path("", views.index, name="index")
]
```

### step 4:

now go back to **lecture 3 folder** and open **urls.py** and edit:

```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('hello/', include("hello.urls"))
]
```



So now if you go back to your website:

```django
python manage.py runserver
```

but this time go to 127.0.0.1/hello

 and you should see hello world!
 




## Render


We don't want to have to include the whole html file into these brackets:

```python
def index(request):
    return HttpResponse("Hello world")
```
    
    
 so we can use render to call a template
 
```python
def index(request):
    return render(request, "<path to template>")
```




# django syntax for IF

<body>
        {% if newyear %}
        <h1>YES</h1>
        {% else %}
        <h1>NO</h1>
        {% endif %}
</body>
    
    

# lecture 5 (move to another page)




Then you need edit urls.py in lecture3 folder with the following:


```django
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path("flights/", include("flights.urls"))
]
```






_This just tell django, that whenever someones visit flights/, i want to direct them to the flight url_

Now we need to create the url:
For that we need to edit urls.py in flights folder. Except this file is not created automatically so we need to create a file caled urls.py

Then add the following code to your new file:

```django
from django.urls import path

from . import views

urlpatterns=[
  
  ]
```


Now go to models.py under flights folder and add following:

```django
from django.db import models
# Create your models here.
class Flight(models.Model):
    origin = models.CharField(max_length=64)
    destination = models.CharField(max_length=64)
    duration = models.IntegerField()
```


every model is going to be a python class


Now we need to make the migration:


`python manage.py makemigrations`


And now we need to apply the migration:

`python manage.py migrate`


to enter the shell:
`python manage.py shell`

then type:

`from flights.models import Flight`

then create a new flight:

`f=Flight(origin="New York", destination="London", duration=415)`

then save this new flight:

`f.save()`


Notice we don't need to write in SQL, because django understands python so we write it in python

if i want to query that flight:

`Flight.objects.all()`


Now exit the shell by type exit()

but the output from the command before isn't very explicit. so we can udpate the model.py file as per below:

```django
from django.db import models
# Create your models here.
class Flight(models.Model):
    origin = models.CharField(max_length=64)
    destination = models.CharField(max_length=64)
    duration = models.IntegerField()
    
    def __str__(self):
        return f"{self.id}:{self.origin} to {self.destination}"
```


so now go back to the shell

`python manage.py shell`

then type:

`from flights.models import Flight`

then type:

`flights = Flight.objects.all()`

then 

`flights`

now we got more relevant info about the flight in question. easier tp read


now we can set up :

`flight = flights.first()`

then 

`flight`

then

`flight.id`

then
`flight.destination`

then
`flight.origin`

then 
`flight.duration`

to access info i need

now if i want to delete that flight
`flight.delete()`

now exit the shell



now lets go back to models.py and create a new class called airport but we also need to change the flights class now:

```python
from django.db import models
from django.db.models.fields import CharField

# Create your models here.
class Airport(models.Model):
    code = models.CharField(max_length=3)
    city = models.CharField(max_length=64)

    def __string__(self):
        return f"{self.city} ({self.code})"



class Flight(models.Model):
    origin = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="departures")
    destination = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="arrivals")
    duration = models.IntegerField()

    def __str__(self):
        return f"{self.id}:{self.origin} to {self.destination}"
```


so now we have updated the python code but we haven't update the DB yet, so we need :

`python manage.py makemigrations`
`python manage.py migrate`











<br />
<br />
<br />
<br />
    
 






![cat5](https://pinklillies.github.io/images/cat5.jfif)
