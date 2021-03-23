---
title: Create a simple Rest API without Django Rest Framework, just pure Django.
date: 2021-03-23 03:00:00 +05:30
modified: 2021-03-23 03:00:00 +05:30
tag: [django, django-rest-framework]
description: Django and Django Rest Framework (aka DRF) is a mostly preferred choice for building production grade Rest API in Django Stack. In this article, we will take a look at, how can we create a Rest API with out even depending on DRF.
image: ""
---

###### Any Django App Consists of three major things, a `Model`, a `URL Path`, a `View`. In here we will create a simple Book store Rest API. A Rest API is just a URL path, where you make an HTTP request, and it returns Data in response.

##### In general API is a bridge, which helps two remote systems to communicate with each other in a limited manner defined by a developer.


## The Introduction -

I hope you are already aware of Django, as in this article, we are not going to cover "how to make a project in Django?".

For this article, you need to create a django project with name `book_store`, and a django app inside it, which name is `book`, project structure looks something like this -

```bash
└── book_store
    ├── book
    │   ├── admin.py
    │   ├── apps.py
    │   ├── __init__.py
    │   ├── migrations
    │   │   └── __init__.py
    │   ├── models.py
    │   ├── tests.py
    │   └── views.py
    ├── book_store
    │   ├── asgi.py
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    └── manage.py
```

When you are done with it, move to the next section, 
Here we will start from Model, then URL & then View.

## Django Models -

As title of this section says, we are going to start from creating our first `Book` model.

Here is our `book/models.py` -
```python
from django.db import models

class Book(models.Model):
    name = models.CharField(max_length=100)
    author = models.CharField(max_length=100)
    published_on = models.DateField()
```

As our model is done, we can now run migration commands, to convert it into a database table.

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

###### Now we are going to create our view function and url path.

## Django URL paths -

Title seems to be a little romantic, but control yourself, as we are going to kiss our urls file.

Open the `book/urls.py` file, and write these lines inside it.

```python
from django.urls import path
from app_name.views import (
    books_api,
    book_create_api,
)

urlpatterns = [
  path('books/', books_api),
  path('book/create/', book_create_api),
]
```

Is this too much for you ? No worries, above `urls.py` is very simple, it has 2 `url` paths, we will create their relative `view` functions in the next section, until then have patience.

1. `books/` this `url` path is to retrieve all the books saved in our database.
2. `book/create/` will take the required data from the client side, and create a `book` entry in our database.


## Django Views -

Let's dig into our `book/views.py` file, and create relevant views for above defined `urls`.

```python
from django.http import JsonResponse
from app_name.models import Book
from django.forms.models import model_to_dict

'books/'
def books_api(request):
    # Retrieve all the books
    books_queryset = Book.objects.all()

    # Convert the queryset into python list
    books_list = list(books_queryset.values())

    # Convert this dictionary into Json Response
    response = JsonResponse(
                books_list, 
                safe=False, 
                status=200
            )
    return response


'book/create/'
def book_create_api(request):

    # Create a book entry
    book_obj = Book.objects.create(
        name=request.POST.get('name'),
        author=request.POST.get('author'),
        published_on=request.POST.get('published_on'),
    )

    # Convert it into a python dictionary
    book_dict = model_to_dict(book_obj)

    # Convert this dictionary into Json Response
    response = JsonResponse(
                book_dict, 
                safe=False, 
                status=200
            )
    return response
```

So finally we have created a simple Rest API with pure django.

##### Note: This post is just for demonstration that, we can build an API wihout relying on any third party framework, just pure django.

Because you will get a lot of functionalities with frameworks like DRF, such as serialization, viewsets, access control, pagination, authentication mechanisms etc.

##### But I highly recommend you to use DRF or Tastypie for creating Django Rest APIs, We will cover it some other day.

Hope you have learned something from this article, thanks for reading.

##### There is so much to learn in the upcoming articles, stick with me, you can follow me on [LinkedIn](https://www.linkedin.com/in/hamhaingaurav/) from [here](https://www.linkedin.com/in/hamhaingaurav/) for more updates.


##### Resources

- [Building API Django](https://books.agiliq.com/projects/django-api-polls-tutorial/en/latest/apis-without-drf.html)