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
