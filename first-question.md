#### Install

1. Clone TolaActivity: https://github.com/toladata-foundation/TolaActivity
2. Go to clone folder, `git checkout new_dev` 
3. Go to local.py 
`except KeyError:`
       \# Fallback for tests without environment variables configured
       \# Depends on os.environ for correct functionality
       DATABASES = {
           'default': {
               'ENGINE': 'django.db.backends.sqlite3',
               'NAME': 'tolaactivity',
           }
       }
       
4. Change to: 
`DATABASES = {`
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'tolaactivity',
           'USER': 'root',
           'PASSWORD': 'root',
           'HOST': 'localhost' ,
           'PORT': '',
       }
       
 #### Deploy locally via virtualenv
 `pip install virtualenv`
 
 `virtualenv —no-site-packages venv`
 
 `virtualenv venv`
 
 `. venv/bin/activate`
 
 Now, you should see "(venv) Andrew-MacBook:TolaActivity andrew$" in your command line
 
`export PATH=$PATH:/usr/local/mysql/bin`

 #### Install Requirements
 
 `pip install -r requirements.txt`, wait for all packages to install.
 
 > Note: If you run into install issues with "mysql" or "ConfigParser" we may need to try an alternative way to install mysql such as:
 1. `brew install mysql`, then `easy _install MySQL-python`
 
```Command "python setup.py egg_info" failed with error code 1 in /private/var/folders/f5/9yy2khcx26qd0h3xgmpd15qm0000gn/T/pip-build-7guQqh/mysqlclient/```

Now run, `python manage.py migrate`


Now go to phpmyadmin and check that you see tables 

#### Create superuser

On venv, run `python manage.py createsuperuser`

Enter `Username`, `Email` and `Password`

<--! tola tola -->

Now run, `python manage.py runserver`


