
# Django - A Web Development Framework in Python  

## Installing Django  

- `pip install Django`  

> This install Django globally on the system  

## Creating Django Project  

> Make sure where you are creating django project  

- `django-admin startproject PROJECT_NAME`  

- `cd PROJECT_NAME`  

- `python manage.py runserver`  

## Apps in Django project  

### Creating App  

- `python manage.py startapp APP_NAME`  

### Link app to Django project  

- Open ***PROJECT_NAME/settings.py***  

- Then scroll down to a python list named ***INSTALLED_APPS***  

> Something familiar like this :arrow_down_small:  

        INSTALLED_APPS = [
            'django.contrib.admin',
            'django.contrib.auth',
            'django.contrib.contenttypes',
            'django.contrib.sessions',
            'django.contrib.messages',
            'django.contrib.staticfiles',
        ]

> Now add app name to the above list like this :arrow_down_small:

        INSTALLED_APPS = [
            'APP_NAME',
            'django.contrib.admin',
            'django.contrib.auth',
            'django.contrib.contenttypes',
            'django.contrib.sessions',
            'django.contrib.messages',
            'django.contrib.staticfiles',
        ]

## Routes

### views.py

- This ***views.py*** files contains number of different views, and we can consider each view is one page  

> A view could be seen like this

        from django.shortcuts import render
        from django.http import HttpResponse

        # Create your views here.

        def index(request):
            return HttpResponse("Hello, world!")
            
> A view is enclosed by a function  

### urls.py  

> It is best practice to create ***urls.py*** file in every app created in the project  

- Now, we need to associate above view with a specific URL  

- Create a ***urls.py*** file in APP_NAME directory which is same directory as ***views.py***  

  - Now create a list called ***urlspattern*** 
  - For each desired URL, add an item to the ***urlpatterns*** list that calls to the path function in ***views.py***
  - **Syntax for path function**
  
    > `path("PATH_NAME", views.VIEW_NAME, name="URL_NAME")`  
    > 
    > 3<sup>rd</sup> argument in path function ***name=""*** is optional
  
  -  **Now _urls.py_ look like this** 

         from django.urls import path  
         from . import views

         urlpatterns = [
                path("", views.index, name="index")
         ]

- Now, Completed creating `urls.py` for this specific application  
- And this `APP_NAME/urls.py` file should be included in the `PROJECT_NAME/urls.py`, then all the urls will be linked to the main project  
- To do this we write ***include("APP_NAME.urls")***, where include is a function we gain access to by also importing include from ***django.urls*** as shown in the ***urls.py*** below:

        from django.contrib import admin
        from django.urls import path, include

        urlpatterns = [
            path('admin/', admin.site.urls),
            path('hello/', include("hello.urls"))
        ]
        
- By doing this, we’ve specified that when a user visits our site, and then in the search bar adds /hello to the URL, they’ll be redirected to the paths inside of our new application.




