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


Every new project needs to have at least one app. To create a new app called hello:

```django
python manage.py startapp flights
```

First thing you need to do after you create your first app is to edit settings.py in airline folder

Under INSTALLED_APPS, add:

`'flights',`


  
  

```django
python manage.py runserver
```







![cat5](https://pinklillies.github.io/images/cat5.jfif)
