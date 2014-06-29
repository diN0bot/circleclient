circleclient
============

.. image:: https://travis-ci.org/qba73/circleclient.svg?branch=master
    :target: https://travis-ci.org/qba73/circleclient
    
Python client library for CircleCI API.

Features
========

* Retrieving information about user
* Listing followed repositories
* Starting build
* Cancelling build

Usage
=====

Retrieve information about User
-------------------------------

.. code:: python

    import os
    import circleclient
    
    
    token = os.environ['API_TOKEN']
    client = circleclient.CircleClient(api_token=token)
    
    # Retrieve User data
    print client.user.get_info()
    

List projects followed by the user
----------------------------------

.. code:: python

   import os
   import circleclient
   
   
   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(api_token=token)
   
   # Retrieve information about projects
   print client.projects.list_projects()
   

Trigger new build in CircleCI
-----------------------------

.. code:: python

   import os
   import circleclient
   
   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(api_token=token)
   
   # Trigger build
   client.build.triger_new(username='<your_username>', project='<your_project>', branch='<branch>')
   
   
Cancel running build
--------------------

.. code:: python

   import os
   import circleclient
   
   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(api_token=token)
   
   # Cancel build
   client.build.cancel(username='<your_username>', project='<your_project>', build_num=<build_number>)
   