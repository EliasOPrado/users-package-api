==========================
Django Samplemed Users Api
==========================

This is a generic sample of code for api test installation.

The steps for installation are as follow:

1. Install `rest_framework`:
  `pip install djangorestframework`

2.Once installed add the `rest_framework` into your `INSTALLED_APPS` in your `settings.py`:

```
INSTALLED_APPS = [
    ...
    'rest_framework',
]
```
3. Install `samplemed_users_api`:
   `pip install samplemed_users_api`

4. Once installed add the `User` app into your `INSTALLED_APPS` in `settings.py`.

```
INSTALLED_APPS = [
    ...
    'rest_framework',
    'Users',
]
```

5. Make db migrations to make the app work:
   `python manage.py makemigrations`
   `python manage.py migrate`

6. Add the urls from `User` app into your main url:

```
from django.conf.urls import include # <========


"""
URL path that will display as default 
admin and the empty path as the API endpoints (router.urls)
"""
urlpatterns = [
    path('admin/', admin.site.urls),
    path('users/', include("Users.urls")), #<======
]

```

7. Go to  `https://your.url.com/users/` and see the endpoints.

