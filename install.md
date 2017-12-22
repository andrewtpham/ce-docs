#### Install

1. Check out the [TolaActivity](https://github.com/toladata-foundation/TolaActivity) repo

`git clone https://github.com/toladata-foundation/TolaActivity.git`

2. To make sure you have the latest changes, go in to the local folder where you cloned the repo  `git checkout new_dev`

3. Open the repo in a text editor and go to: `local.py` file

2. Find the following code snippet

       except KeyError:`
           \# Fallback for tests without environment variables configured
           \# Depends on os.environ for correct functionality

and highlight the following:
```
           DATABASES = {
               'default': {
                   'ENGINE': 'django.db.backends.sqlite3',
                   'NAME': 'tolaactivity',
               }
           }
```
3. Replace with:

   ```
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'tolaactivity',
           'USER': 'root',
           'PASSWORD': 'root',
           'HOST': 'localhost' ,
           'PORT': '',
       }
   ```

#### Deploy locally via virtualenv

   `pip install virtualenv`

   `virtualenv —no-site-packages venv`

   `virtualenv venv`

   `. venv/bin/activate`

   Now, you should see "\(venv\) Andrew-MacBook:TolaActivity andrew$" in your command line

`export PATH=$PATH:/usr/local/mysql/bin`

#### Install Requirements

`pip install -r requirements.txt`, wait for all packages to install.

> Note: If you run into install issues with "mysql" or "ConfigParser" we may need to try an alternative way to install mysql such as:  
>  1. `brew install mysql`, then `easy _install MySQL-python`

`Command "python setup.py egg_info" failed with error code 1 in /private/var/folders/f5/9yy2khcx26qd0h3xgmpd15qm0000gn/T/pip-build-7guQqh/mysqlclient/`

Now run, `python manage.py migrate`

Now go to phpmyadmin and check that you see tables

#### Create superuser

On venv, run `python manage.py createsuperuser`

Enter `Username`, `Email` and `Password`

&lt;--! tola tola --&gt;

Now run, `python manage.py runserver`

