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
