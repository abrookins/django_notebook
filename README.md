
django_notebook
---------------

While there doesn't seem to be an easy way cause `python manage.py shell` to start IPython notebook, you can load an IPython extension that performs the imports that an IPython session needs to run Django.

This is such an extension. You can install it by executing this command from within IPython:

`%install_ext https://raw.github.com/abrookins/django_notebook/master/django_notebook.py`

This will download the `django_notebook.py` module into `~/.ipython/extensions/django_notebook.py`. (The extension merely attempts to load Django whenever you start IPython, unless an ImportError occurs.)

After installing the extension, add it to your IPython RC file. This is probably at `~/.ipython/profile_default/ipython_config.py`. If you don't have one, you can use this command to create one with IPython (from the terminal shell, not within IPython):

`ipython profile create`

Then edit the created (or existing) `ipython_config.py` file and add the following line somewhere after the line `c = get_config()`:

`c.InteractiveShellApp.extensions = [
    'django_notebook'
]`

(Or just append `'django_notebook'` to the existing extensions list if it exists.)

Now you should be able to run `ipython notebook` from within a Django project and have access to all of the Django and project-related modules. 
