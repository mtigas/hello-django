hello-django
============

The minimum "hello world" for Django 1.4. Views only, no code having anything
to do with model/database/etc.

## Setup:

Assuming Django is installed (`pip install django` or `easy_install django`),
these are the commands that were run to create this repo once you are `cd`'d
into a directory you want to contain your Django project (in my case, the
directory that became the root of this repo):

    django-admin.py startproject mysite
    cd mysite
    python manage.py startapp myapp

(The result of these steps, unedited, was the [first code commit](https://github.com/mtigas/hello-django/commit/255d88661c025874d5e47c2e1bc5a5d8d624d265).)

Then `mysite/myapp/views.py` was edited to contain [the little bit of code
you see inside that file now.](https://github.com/mtigas/hello-django/blob/master/mysite/myapp/views.py)

`mysite/mysite/urls.py` was edited to add the following line inside the
`patterns('', ...)`  bit.

    url(r'^$', 'myapp.views.hello'),

(Those steps comprised [the next commit](https://github.com/mtigas/hello-django/commit/07544b4f17f9bfc3c42874ea0b6b67f84c18e2c4).)

That's it.

## Hello World

From inside the repo root:

    cd mysite
    python manage.py runserver

Then open http://127.0.0.1:8000/ .

## Notes

This doesn't use [virtualenv](http://iamzed.com/2009/05/07/a-primer-on-virtualenv/)
or any other "best practices" things to contain the Django installation. This
doesn't explain anything other than how to get plain Python code spitting out
an `HttpResponse` that says "Hello, world" at the / URL.
