
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

**Docker** is a computer program that performs operating-system-level virtualization also known as containerization. it is developed by .. _Docker,Inc: https://www.docker.com/what-docker .

Abaco pulls images for its actors from the public Docker Hub. To register actors you will need to publish images on Docker Hub, which requires a docker account `Click Here: https://hub.docker.com/`__ . 

Install the TACC Cloud Python SDK
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To interact with the Tacc hosted Aboaco platform in Python, we will install the Python SDK. Simply run:

.. code-block:: bash

  $ pip install agavepy
  





