# django_app_boilerplate
This is a boilerplate to get you started with a (what I believe) to be one of the best ways to format and organize your Django project.
![alt text](https://miro.medium.com/max/1400/1*KwSbyYyqaukruQVofd1HTQ.jpeg "Django")

## Small guide on how to use this boilerplate

### The Folders
#### Apps
This folder is meant for you to store all of your Django Apps in, once you create
a folder for your Django app make sure to add it to INSTALLED_APPS in the settings which is located in ```config/settings/base.py```

#### Config
This folder is storing all of the different files needed for the configuration of the Django project, in here we have the ```urls.py``` where you should import all your ```urls.py``` from all of your differnet apps in the ```apps``` folder.

Within the ```settings``` folder we have
1. ```base.py```: contains the settings for the base app which then gets extended into either production or local
2. ```local.py```: extends ```base.py``` with extra settings which will only be present in the local version of the application
3. ```prod.py```: extends ```base.py``` with extra settings which will only be present in the production version of the application

#### Requirements

In requirements there are three files. This is to make the installation process easier for python enviornments
1. ```base.txt```:python packages needed for both local and text
2. ```local.txt```: python packages needed for only local
3. ```production.txt```: python packages needed for only production


### Starting the boilerplate

#### Requirements:
* Python 3.6 or higher
* Postgres


1. ```touch .env``` To create a environment file with the following:
```
bash
DEBUG=true
SECRET_KEY=[KEY]
DJANGO_SETTINGS_MODULE=config.settings.local
ALLOWED_HOSTS=0.0.0.0,localhost,127.0.0.1
CORS_WHITELIST=http://0.0.0.0:3000
DATABASE_URL=postgres://[user]:[password]@[ip or localhost]:5432/[database]
EMAIL_USE_TLS=True
EMAIL_PORT=587
EMAIL_HOST=smtp.domain.com
EMAIL_HOST_USER=[EMAIL]
EMAIL_HOST_PASSWORD=[PASSWORD]
EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
DEFAULT_FROM_EMAIL=[DEFAULT_EMAIL]
```

2. Install required python packages:
```
pip3 install -r requirements/local.txt
```

3. Start up django:
```
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```
