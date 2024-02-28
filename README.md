## TLDR
Basically you just define your models in your app's models.py and then do <br>
`python manage.py makemigrations` <br>
`python manage.py migrate` <br>
and it'll generate the tables in the database.
When you want to make changes to the database tables (e.g. add attributes) you just modify the models.py and run those 2 commands again

## Models
![alt text](https://i.imgur.com/aL7qNSA.png)<br>
```python
class User(models.Model):
    username = models.CharField(max_length=100, primary_key=True)
    password = models.CharField(max_length=100)
    email = models.EmailField(unique=True)
    role = models.CharField(max_length=100)
```
vaguely translates to
```SQL
CREATE TABLE User (
    username varchar(100),
    password varchar(100),
    ...
);
```
refer to the [django model field reference](https://docs.djangoproject.com/en/5.0/ref/models/fields/#field-types) on the fields (datatype) you can use/what the fields used are <br>

## Querying
Found [the docs](https://docs.djangoproject.com/en/5.0/topics/db/queries) pretty useful, should have a pretty good understanding by reading up to and including the `Retrieving objects` part
