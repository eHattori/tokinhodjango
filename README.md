# TOKINHO DJANGO OAUTH2


## Install

```
pip install -r requirements.txt
```

## Create User and Run

```
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

## Login 
```
http://localhost:8000/admin
```

## Register an application

```
http://localhost:8000/o/applications/
```

Click on the link to create a new application and fill the form with the following data:

Name: just a name of your choice
Client Type: confidential
Authorization Grant Type: Resource owner password-based
Save your app!


##  Get your token and use your API

```
curl -X POST -d "grant_type=password&username=<user_name>&password=<password>" -u"<client_id>:<client_secret>" http://localhost:8000/o/token/
```

 Response should be something like:

```
{
    "access_token": "<your_access_token>",
    "token_type": "Bearer",
    "expires_in": 36000,
    "refresh_token": "<your_refresh_token>",
    "scope": "read write groups"
}
```


## Test yout token

```
curl -H "Authorization: Bearer <your_access_token>" http://localhost:8000/users/
```
