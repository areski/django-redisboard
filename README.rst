=============================
    django-redisboard
=============================


Redis monitoring drop-in application using django admin.

Features
========

* Sever statistics in the admin changelist
* Key summary in the inspect view
* Value introspection with pagination for lists and sorted sets


Installation guide
==================

Install from pypi, with pip::

    pip install django-redisboard
    
Or with setuptools::

    easy_install django-redisboard

Add ``redisboard`` to ``INSTALLED_APPS``::

    INSTALLED_APPS += ("redisboard", )

After that you need to run::

    manage.py syncdb

Or if you use south you can migrate this app::

    manage.py migrate redisboard

Then you can add redis servers in the admin. You will see the stats in the changelist.

Optional django settings
========================

REDISBOARD_DETAIL_FILTERS
-------------------------

REDISBOARD_DETAIL_FILTERS - a list of regular expressions to match against the keys in the server 
details colum. Eg, to only show uptime and list of active databases::

    REDISBOARD_DETAIL_FILTERS = ['uptime.*', 'db.*']

To show all the details just use:: 
    
    REDISBOARD_DETAIL_FILTERS = ['.*']

REDISBOARD_ITEMS_PER_PAGE
-------------------------

REDISBOARD_ITEMS_PER_PAGE - default 1000. Used for paginating the items from a list or a sorted set.

Screenshots
===========

Changelist:

.. image:: https://github.com/downloads/ionelmc/django-redisboard/screenshot.png

Inspect page:

.. image:: https://github.com/downloads/ionelmc/django-redisboard/redisboard-inspect.png
