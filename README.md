[office-doc]:https://django-registration-redux.readthedocs.io/en/latest/index.html
[templates]: https://github.com/macropin/django-registration/tree/master/registration/templates/registration

django를 이용한 회원가입 및 계정관련 third-party library

- django-redux 설치

```python
pip install django-registration-redux
```

INSTALLED_APP

```python
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_HOST_USER = 'yourgmail@gmail.com'
EMAIL_HOST_PASSWORD = 'yourpassword'
EMAIL_PORT = 587
EMAIL_USE_TLS = True

INSTALLED_APP[
  	'django.contrib.sites',
    'registration',  # should be immediately above 'django.contrib.admin'
  	'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',    
    'myapp',
  ]		

#DJANGO REGISTRATION REDUX SETTINGS
ACCOUNT_ACTIVATION_DAYS = 7
REGISTRATION_AUTO_LOGIN = True
SITE_ID = 1
LOGIN_REDIRECT_URL = '/'
```

- 공식 사이트에서는 admin 위에 registration을 위치시키라고 권고하지만, 다른 위치에 지정해도 문제는 없었음

- password 관련 설정에서 email verification이 일어나기 때문에 위와 같이 smtp 설정을 하거나 아래와 같이 EMAIL_BACKEND 설정이 필요함

  ```python
  EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
  ```

  