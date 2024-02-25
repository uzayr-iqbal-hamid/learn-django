# learn-django

### Let's start by setting up a virtual environment.
In the terminal / VScode terminal:<br>
Linux:<br>
```shell
sudo apt install pipenv
```

Windows:<br>
```shell
pip install pipenv
```

Then, common commands:<br>
```shell
pipenv install
```
<br>This installs all the necessary files (pipfile)
<br><br>
### Install Django:<br>
In terminal:

```shell
pipenv install Django
```

Open Shell:<br>
```shell
pipenv shell
```

To ensure that you have installed Django, run:<br>
```shell
pip show Django
```
<br><br>
### Starting a new project:<br>
In terminal:

```shell
django-admin startproject mysite .
```
<br>Open it on localhost:8000<br>

```shell
python manage.py runserver 0.0.0.0:8000
```

<br>Migrate the changes:<br>

```shell
python manage.py migrate
```

<br>Create a super user:<br>

```shell
python manage.py createsuperuser
```
<br>Enter your username and password, confirm password.<br>
<br>To start the app:<br>

```shell
python manage.py startapp feed
```
<br>

Go to [settings.py](mysite/settings.py),
Add 'feed', item in the INSTALLED_APPS = []
![image](https://github.com/uzayr-iqbal-hamid/learn-django/assets/134723279/59c01f01-bbf4-45f4-a5ec-a6459265785c)
<br>
In terminal

```shell
django-admin startproject mysite .
```
again.<br>

<br>Go to [models.py](feed/models.py), and type:

```python
class Post(models.Model):
  text = models.CharField(max_length=140, blank=False, null=False)
```
<br>
In terminal:

```shell
python manage.py makemigrations
```

```shell
python manage.py migrate
```

```shell
python manage.py runserver 0.0.0.0:8000
```
<br>

Go to [admin.py](feed/admin.py), and type:
  - ```python
    from .models import Post
    
    class PostAdmin(admin.ModelAdmin):
      pass

    admin.site.register(Post, PostAdmin)
    ```
<br>
Refresh localhost:8000
