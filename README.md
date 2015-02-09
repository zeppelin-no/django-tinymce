django-tinymce
===

**django-tinymce** is a Django application that contains a widget to render a form field as a TinyMCE editor.

file_browser_callback
===
Look at the link below to make file_browser_callback work with this version 
http://pixabay.com/en/blog/posts/direct-image-uploads-in-tinymce-4-42/

=> you have to write your own upload function supported by your backend


WARNING:
===
v2.0 uses TinyMCE v4.x and is not backwards compatible w/ previous versions.

Quickstart:
===

Install django-tinymce:

    $ pip install -e git+https://github.com/zeppelin-no/django-tinymce.git#egg=django-tinymce

Add tinymce to INSTALLED_APPS in settings.py for your project:

    INSTALLED_APPS = (
        ...
        'tinymce',
    )

Add tinymce.urls to urls.py for your project:

    urlpatterns = patterns('',
        ...
        (r'^tinymce/', include('tinymce.urls')),
    )

In your code:

    # Python:
        forms.CharField(widget=TinyMCE(attrs={...}, mce_attrs={'file_browser_callback': 'file_browser_function'}))
        
    // JavaScript:
    <script>
    function file_browser_function(field_name, url, type, win) {
        ....
    }
    </script>

**django-tinymce** uses staticfiles so everything should work as expected, different use cases (like using widget instead of HTMLField) and other stuff is available in documentation.

Documentation:
===
http://django-tinymce.readthedocs.org/

License (and related information):
===
Originally written by Joost Cassee.

This program is licensed under the MIT License (see LICENSE.txt)
