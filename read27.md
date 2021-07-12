# Django Models

Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields



## Fields

Model can have an arbitrary number of fields, of any type each one represents a column of datatables. 

#### Common field arguments

- help_text: Provides a text label for HTML forms (e.g. in the admin site), as described above.
- verbose_name: A human-readable name for the field used in field labels. If not specified, Django will infer the default verbose name from the field name.
- default: The default value for the field. This can be a value or a callable object, in which case the object will be called every time a new record is created.
- null: If True, Django will store blank values as NULL in the database for fields where this is appropriate (a CharField will instead store an empty string). The default is False.
- blank: If True, the field is allowed to be blank in your forms. The default is False, which means that Django's form validation will force you to enter a value. This is often used with null=True , because if you're going to allow blank values, you also want the database to be able to represent them appropriately.
- choices: A group of choices for this field. If this is provided, the default corresponding form widget will be a select box with these choices instead of the standard text field.
- primary_key: If True, sets the current field as the primary key for the model (A primary key is a special database column designated to uniquely identify all the different table records). If no field is specified as the primary key then Django will automatically add a field for this purpose.

## Common field types 

- CharField is used to define short-to-mid sized fixed-length strings. 

- TextField is used for large arbitrary-length strings.

- IntegerField is a field for storing integer (whole number) values, and for validating entered values as integers in forms.

- DateField and DateTimeField are used for storing/representing dates and date/time information , and to set a default date that can be overridden by the user.

- EmailField is used to store and validate email addresses.

- FileField and ImageField are used to upload files and images respectively (the ImageField adds additional validation that the uploaded file is an image). These have parameters to define how and where the uploaded files are stored.

- AutoField is a special type of IntegerField that automatically increments. A primary key of this type is automatically added to your model if you don’t explicitly specify one.

- ForeignKey is used to specify a one-to-many relationship to another database model (e.g. a car has one manufacturer, but a manufacturer can make many cars). The "one" side of the relationship is the model that contains the "key" (models containing a "foreign key" referring to that "key", are on the "many" side of such a relationship).

### Methods

Minimally, in every model you should define the standard Python class method `__str__()` to return a human-readable string for each object. This string is used to represent individual records in the administration site (and anywhere else you need to refer to a model instance). Often this will return a title or name field from the model.

```python
def __str__(self):
    return self.field_name
```

Another common method to include in Django models is get_absolute_url(), which returns a URL for displaying individual model records on the website (if you define this method then Django will automatically add a "View on Site" button to the model's record editing screens in the Admin site). A typical pattern for get_absolute_url() is shown below.

```python
def get_absolute_url(self):
    """Returns the url to access a particular instance of the model."""
    return reverse('model-detail-view', args=[str(self.id)])
```

## Django Admin Site

it can be used for  build a site area that can create, view, update, and delete records. 

### Registering models

 open admin.py in the catalog application (/locallibrary/catalog/admin.py). It currently looks like this — note that it already imports django.contrib.admin:

```python
from django.contrib import admin

```

Register the models by copying the following text into the bottom of the file. This code imports the models and then calls admin.site.register to register each of them.

```python
from .models import Author, Genre, Book, BookInstance

```

## Creating a superuser

   to view and create records you will need this user to have permissions to manage all our objects. 