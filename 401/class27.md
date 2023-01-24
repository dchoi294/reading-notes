# Class 27 Reading Notes

## Using Models

Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata.  

**Fields**  
A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables. Each database record (row) will consist of one of each field value.  
The field name is used to refer to it in queries and templates. Fields also have a label, which is specified using the verbose_name argument (with a default value of None). If verbose_name is not set, the label is created from the field name by replacing any underscores with a space, and capitalizing the first letter (for example, the field my_field_name would have a default label of My field name when used in forms).  

**Metadata**  
One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type. You do this by specifying the match order in a list of field names to the ordering attribute, as shown above. The ordering will depend on the type of field (character fields are sorted alphabetically, while date fields are sorted in chronological order). As shown above, you can prefix the field name with a minus symbol (-) to reverse the sorting order.  

**Methods**  
Minimally, in every model you should define the standard Python class method `__str__()` to return a human-readable string for each object. This string is used to represent individual records in the administration site (and anywhere else you need to refer to a model instance). Often this will return a title or name field from the model.  
Another common method to include in Django models is get_absolute_url(), which returns a URL for displaying individual model records on the website (if you define this method then Django will automatically add a "View on Site" button to the model's record editing screens in the Admin site).  

**Genre Model**  
Copy the Genre model code shown below and paste it into the bottom of your models.py file. This model is used to store information about the book category — for example whether it is fiction or non-fiction, romance or military history, etc. As mentioned above, we've created the genre as a model rather than as free text or a selection list so that the possible values can be managed through the database rather than being hard coded.  

**Book model**  
Copy the Book model below and again paste it into the bottom of your file. The Book model represents all information about an available book in a general sense, but not a particular physical "instance" or "copy" available for loan. The model uses a CharField to represent the book's title and isbn. For isbn, note how the first unnamed parameter explicitly sets the label as "ISBN" (otherwise, it would default to "Isbn"). We also set the parameter unique as true to ensure all books have a unique ISBN (the unique parameter makes the field value globally unique in a table). The model uses TextField for the summary, because this text may need to be quite long.  

## Django Admin

The Django admin application can use your models to automatically build a site area that you can use to create, view, update, and delete records. This can save you a lot of time during development, making it very easy to test your models and get a feel for whether you have the right data. The admin application can also be useful for managing data in production, depending on the type of website. The Django project recommends it only for internal data management (i.e. just for use by admins, or people internal to your organization), as the model-centric approach is not necessarily the best possible interface for all users, and exposes a lot of unnecessary detail about the models.  

**Registering models**  

- First, open admin.py in the catalog application (/locallibrary/catalog/admin.py). It currently looks like this — note that it already imports django.contrib.admin  
- Register the models by copying the following text into the bottom of the file. This code imports the models and then calls admin.site.register to register each of them.  
This is the simplest way of registering a model, or models, with the site. The admin site is highly customizable, and we'll talk more about the other ways of registering your models further down.  

In order to log into the admin site, we need a user account with Staff status enabled. In order to view and create records we also need this user to have permissions to manage all our objects. You can create a "superuser" account that has full access to the site and all needed permissions using manage.py.  

`python3 manage.py createsuperuser`
`python3 manage.py runserver`


Reference[Using Models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models#model_primer)  
Reference[Django Admin](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)  

## Things I want to know more about



[Back to Home](../../README.md)
