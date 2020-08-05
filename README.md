# cheat
all my cheat files

------------------
# Start Django :

```bash
# crete virtual env
virtualenv -p python3.8 $venv

cd $venv
# activate the virtual env
source bin/activate
mkdir src
cd src
# install Django on this venv
pip3 install django

# crete outline.md to reate structer of the project 
# Bla Bla Bla

# Now start Django project 
django-admin startproject project .
# run the server on 172.0:8000
python3 manage.py runserver

# Open http://127.0.0.1:8000/ 
The install worked successfully! Congratulations!
```

```bash

python3 manage.py migrate
# creteDjango Admin (superuser)
python3 manage.py createsuperuser
------------------------------------------
Username (leave blank to use 'taha'): admin
Email address: 
Password: d7@nG0
Password (again): d7@nG0
This password is too short. It must contain at least 8 characters.
Bypass password validation and create user anyway? [y/N]: y
Superuser created successfully.
------------------------------------------
# Crete App 

python3 manage.py startapp $coffe

# When you add app to your Django go to project/settings.py
# and add it to 

INSTALLED_APPS = [
    ... ,
    ... ,
    # add 
    '$cofe',
    
]

# Create Models 
# go to models.py on your app
class Coffe(models.Model):
    
    COFName = models.CharField(max_length=100)
    COFDescription = models.TextField()
    COFPrice = models.DecimalField(max_digits=4, decimal_places=3)
    
    def __str__(self):
        return self.COFName


python3 manage.py makemigrations
python3 manage.py migrate

# time to add this toadmin.py always on your app 
from .models import Coffe

admin.site.register(Coffe)

# to change the name variable in the web site use :
verbose_name=('title') # on your model variable

```


