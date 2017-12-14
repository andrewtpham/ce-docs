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
 
 `pip install -r requirements.txt`
 
 



