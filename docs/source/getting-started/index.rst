
.. _getting-started:

===================
Getting Started
===================

This guide will walk through the initial steps of getting account, and preparing yourself for the agave user guide tutorial.

.. contents:: :local:

------------------------------------------
Account Creation and Software Installation
------------------------------------------

Create a TACC account
^^^^^^^^^^^^^^^^^^^^^

Abaco is an API platform hosted by the Texas Adavanced Computing Center(TACC). TACC designs and deploys the world's most powerful advanced computing technologies and innovative software solutions to enable reseachers to anwser complex questions.

To use the hosted Abaco service, please create a `TACC account <https://portal.tacc.utexas.edu/account-request>`__ .

Create a Docker account
^^^^^^^^^^^^^^^^^^^^^^^^

**Docker** is a computer program that performs operating-system-level virtualization also known as containerization. it is developed by  `Docker,Inc <https://www.docker.com/what-docker>`__ .

Abaco pulls images for its actors from the public Docker Hub. To register actors you will need to publish images on Docker Hub, which requires a docker account `Click Here <https://hub.docker.com/>`__ . 

Install the TACC Cloud Python SDK
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To interact with the Tacc hosted Aboaco platform in Python, we will install the Python SDK. Simply run:

.. code-block:: bash

  $ pip install agavepy
  
-----------------------
Create an OAuth Client
-----------------------

Authentication and authorization to the TACC Cloud APIs uses OAuth2`_, a widely-adopted web standard. Our implementation of Oauth2 is designed to give you the flexibility you need to script and automate use of TACC Cloud while keeping your access credentials and digital assets secure.

This is covered in great detail in our Developer Documentation but some key concepts will be highlighted here,interleaved with Python code.

The first step is to create a python object called ``ag`` pointing to an API server. Your project likely has its own API server, which are discoverable using the ``tenants-list --rich`` command in the TACC cloud CLI. for now, we can assume (http://api.tacc.utexas.edu)the default value will work for you.

First, type in the following line in your shell:

.. code-block:: bash

  >>> from agavepy.agave import Agave


Next, type in the following line in your shell:

.. code-block:: bash

   >>> ag = Agave(api_server='http://api.tacc.utexas.edu')

Once the object is instantiated, interact with it according to the API documentation and your specific usage needs.Create a new Oauth client

.. code-block:: bash

  >>> ag = Agave(api_server='https://api.tacc.utexas.edu',
  ...            username='your username',
  ...            password='your password')
  >>> ag.clients.create(body={'clientName': 'enter a client name'})

You use the consumerKey and consumerSecret to generate Oauth tokens, which are temporary credentials that you can use in place of putting your real credentials into code that is scripting against the TACC APIs.






