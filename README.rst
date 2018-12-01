.. image:: https://travis-ci.com/factoriomaps/factoriomaps-web.svg?branch=master
    :target: https://travis-ci.com/factoriomaps/factoriomaps-web
.. image:: https://coveralls.io/repos/github/factoriomaps/factoriomaps-web/badge.svg?branch=master
    :target: https://coveralls.io/github/factoriomaps/factoriomaps-web?branch=master

.. note::
    These docs are still a WIP, please provide feedback for better docs!

QuickStart
----------

To get the server started, run the following commands.

.. code-block:: bash

    pip install -r requirements.txt
    python manage.py migrate
    python manage.py runserver --settings=factoriomaps.settings.dev-example.py



Django Developer Setup
----------------------

1. Settings File
================

The settings files are located in factoriomaps/settings/. We've provided an
example settings file to use as a guide, please copy this file into a new
settings file & modify that for your personal use. To use your copied settings
file, simply run your manage.py commands with the --settings flag or set
the DJANGO_SETTINGS_MODULE environment variable.

.. warning::
    Please git ignore the settings file you use for personal use. Do not push this
    to a repository.

`Django settings docs`_.

.. _`Django settings docs`: https://docs.djangoproject.com/en/2.1/topics/settings/

2. Database Setup
=================

We are using Postgres as our database technology. It is recommended, although
not required, that you configure one. This can be done by either installing
Postgres on your `local system`_ or using a Docker_ container.

Once that is complete, all that is left is configuring the Django settings
file to use your newly installed database. To do so, simply create or
modify the DATABASE variable in your settings file like so:

.. code-block:: python

    DATABASES = {
        'default': {
            'HOST': 'localhost',
            'ENGINE': 'django.db.backends.postgresql_psycopg2',
            'NAME': '<database_name>',
            'USER': '<user>',
            'PASSWORD': '<password>',
            'PORT': 5432
        }
    }

Once this is complete, you will need to rerun migrations in your newly created
database:

.. code-block:: bash

    python manage.py migrate


`Django database docs`_.

.. _`Django database docs`: https://docs.djangoproject.com/en/2.1/ref/databases/

.. _Docker: https://hub.docker.com/_/postgres/
.. _`local system`:  https://www.postgresql.org/docs/9.3/tutorial-install.html



To-Do's
-------

Write more tests!
