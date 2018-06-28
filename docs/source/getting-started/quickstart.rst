.. _getting-started
===================
Abaco Quickstart
===================

Writing a Python Function
-------------------------

Now, that we have the Agavpy package install, lets create a docker image that contains they python function and executes it as part of the default command. First create a python file called `Example.py` and paste the same code below in it.

.. code-block:: bash

  >>> def string_count():
         message = "Hey my name is john"
         words = message.split(' ')
         word_count = len(words)
         print('Number of words is: ' + str(word_count))
     string_count()

Building Images From a Dockerfile
----------------------------------

Next, create a docker image that contains the python function and execute it as part of the default command

We can build images from a text file called a Dockerfile. You can think of a Dockerfile as a recipe for creating images. The instructions within a dockerfile either add files/folders to the images, add metadata to the image, or both.

The FROM instruction
^^^^^^^^^^^^^^^^^^^^^
we can use the ``FROM`` instruction to start our new image from a known image. this should be the first line of our Dockerfile.

.. code-block:: bash

  FROM python

The ADD instruction
^^^^^^^^^^^^^^^^^^^^^

We can also add local files to our image using the ``ADD`` instruction. We can add a the file ``Example.py`` in our local directory to the ``Users/kwhitley/PycharmProjects/Test`` directory in our container with the following instruction:

.. code-block:: bash

  ADD Example.py /Users/kwhitley/PycharmProjects/Test


The last step is write the command from running the application, which is simply - ``python ./Example.py``. We use the ``CMD`` command to do that:

.. code-block:: bash

  CMD ["python", "./Example.py"]

The primary purpose of ``CMD`` is to tell the container which command it should run when it is started. With that, our ``Dockerfile`` is now ready. This is what is looks like:

.. code-block:: bash

  FROM python

  ADD Example.py /Users/kwhitley/PycharmProjects/Test

  CMD ["python", "./Example.py"]


Now that we have our ``Dockerfile``, we can build our image. the `docker build` command does the heavy lifting of creating a Docker image from a ``Dockerfile``.

Actors
-------

Now that we going to register a docker container as an actor, to do this we have to an API client and once we have this you only have to do the set up once!

To register a actor using the agavepy library, we use the `actors.add()` method and pass the same arguments through the `body` parameter. For example,

.. code-block:: bash

  >>> from agavepy.agave import Agave
  >>> ag = Agave(api_server='https://api.tacc.utexas.edu', token='<access_token>')
  >>> reactor = {"image": "abacosamples/test", "name": "test", "description": "My test actor using the abacosamples image r   egistered using agavepy.", "default_environment":{"key1": "value1", "key2": "value2"} }
  >>> ag.actors.add(body=reactor)
  
To get the message from `Abaco` do the following:

.. code-block:: bash

from agavepy.actors import get_contex
def string_count():
    context = get_context()
    try:
        message = context['raw_message']
    except Exception as e:
        print("Got an exception parsing message. Aborting. Exception: {}".format(e))
    words = message = "Hey my name is john"
         words = message.split(' ')
         word_count = len(words)
         print('Number of words is: ' + str(word_count))
     string_count()
     
