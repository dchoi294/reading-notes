# Class 26 Reading Notes

Django is a Python-based web framework used by millions of developers and billions of consumers through popular apps like Instagram. It is open source, meaning the code is available for free on Github and can be downloaded onto any developer’s computer and used alongside the official documentation. Deﬁne your data models entirely in Python. You get a rich, dynamic database-access API for free — but you can still write SQL if needed.  

**URLs and views**  

A clean, elegant URL scheme is an important detail in a high-quality web application. Django encourages beautiful URL design and doesn’t put any cruft in URLs, like .php or .asp.  

```
from django.urls import path

from . import views

urlpatterns = [
    path('bands/', views.band_listing, name='band-list'),
    path('bands/<int:band_id>/', views.band_detail, name='band-detail'),
    path('bands/search/', views.band_search, name='band-search'),
]
```

**Templates**  

Django’s template language is designed to strike a balance between power and ease. It’s designed to feel comfortable and easy-to-learn to those used to working with HTML, like designers and front-end developers. But it is also flexible and highly extensible, allowing developers to augment the template language as needed.

```
<html>
  <head>
    <title>Band Listing</title>
  </head>
  <body>
    <h1>All Bands</h1>
    <ul>
    {% for band in bands %}
      <li>
        <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
        {% if band.can_rock %}<p>This band can rock!</p>{% endif %}
      </li>
    {% endfor %}
    </ul>
  </body>
</html>
```

**Forms**  

```
from django import forms

class BandContactForm(forms.Form):
    subject = forms.CharField(max_length=100)
    message = forms.CharField()
    sender = forms.EmailField()
    cc_myself = forms.BooleanField(required=False)
```

Reference[Getting started with Django](https://www.djangoproject.com/start/)  
Reference[How Django Works Behind the Scenes](https://wsvincent.com/how-django-works-behind-the-scenes/)  

## Things I want to know more about



[Back to Home](../../README.md)
