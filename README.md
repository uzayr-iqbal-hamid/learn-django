# learn-django

### Let's start by setting up a virtual environment.
In the terminal / VScode terminal:<br>
Linux:<br>
```sudo apt install pipenv```

Windows:<br>
<code>pip install pipenv</code>

Then, common commands:<br>
<code>pipenv install</code>
<br>This installs all the necessary files (pipfile)
<br><br>
### Install Django:<br>
<code>pipenv install Django</code>

Open Shell:<br>
<code>pipenv shell</code>

To ensure that you have installed Django, run:<br>
<code>pip show Django</code>
<br><br>
### Starting a new project:<br>
<code>django-admin startproject mysite .</code><br>
<br>Open it on localhost:8000<br>
<code>python manage.py runserver 0.0.0.0:8000</code><br>
<br>Migrate the changes:<br>
<code>python manage.py migrate</code><br>
<br>Create a super user:<br>
<code>python manage.py createsuperuser</code><br>
<br>Enter your username and password, confirm password.<br>
<br>To start the app:<br>
<code>python manage.py startapp feed</code><br>
<br>
Go to [settings.py](mysite/settings.py),
  - Add 'feed', item in the INSTALLED_APPS = []
    ![image](https://github.com/uzayr-iqbal-hamid/learn-django/assets/134723279/59c01f01-bbf4-45f4-a5ec-a6459265785c)
    <br>Run: <code>python manage.py runserver 0.0.0.0:8000</code> again.<br>
<br>Go to [models.py](feed/models.py),
  - ```python
    class Post(models.Model):
      text = models.CharField(max_length=140, blank=False, null=False)
    ```
<br>
<code>python manage.py makemigrations</code><br>
<code>python manage.py migrate</code><br>
<code>python manage.py runserver 0.0.0.0:8000</code><br>
<br>

Go to [admin.py](feed/admin.py), 
  - ```python
    from .models import Post

    class PostAdmin(admin.ModelAdmin):
      pass

    admin.site.register(Post, PostAdmin)
    ```
<br>
Refresh localhost:8000
