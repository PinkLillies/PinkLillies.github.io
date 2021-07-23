# Django - Basics

## Commands

To create a new project:

```django
django-admin startproject airline
```

_(note: you need to be in the folder that contains django-admin.exe)_

then go to the directory and open Visual Studio Code:

`cd airline`

`code .`


Every new project needs to have at least one app. To create a new app called flights:

```django
python manage.py startapp flights
```

First thing you need to do after you create your first app is to edit settings.py in airline folder

Under INSTALLED_APPS, add:

`'flights',`

Then you need edit urls.py in airline folder with the following:

```django
from django.contrib import admin
from django.urls import include,path
urlpatterns=[
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






  
  

```django
python manage.py runserver
```







![cat5](https://pinklillies.github.io/images/cat5.jfif)
