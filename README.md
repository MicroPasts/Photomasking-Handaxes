PyBossa photo masking application for Olduvai Gorge Handaxes
============================================================

This application has three files:

*  createTasks.py: for creating the application in PyBossa, and fill it with some tasks.
*  template.html: the view for every task and deal with the data of the answers.
*  tutorial.html: a simple tutorial for the volunteers.

![alt screenshot](http://micropasts.org/wp-content/uploads/2014/09/OlduvaiApp.png)

Funded by
=========
![AHRC funded](http://oac.lib.bris.ac.uk/Dserve/images/AHRC%20Logo%20Gray%20LScape2.JPG)

Funded Partners
===============
![British Museum](http://finds.org.uk/images/logos/bm_logo.png)
![UCL](http://crowdsourced.micropasts.org/static/img/black.jpg)
![Portable Antiquities Scheme](http://www.dayofarchaeology.com/wp-content/uploads/2011/05/pasrgbsize4.jpg)

Testing the application
=======================

You need to install the pybossa-client first (use a virtualenv and this needs boto):

```bash
    $ pip install -r requirements.txt
    $ cp s3_settings.py.tmpl s3_settings.py
```

In the settings file, just set the root bucket name, your access key  and secret key.

Then, you can follow the next steps:

*  Edit the s3_settings.py file with your S3 credentials
*  Create an account in PyBossa
*  Copy under your account profile your API-KEY
*  Run python createTasks.py -u http://crowdcrafting.org -k API-KEY
*  Open with your browser the Applications section and choose the FlickrPerson app. This will open the presenter for this demo application.

Documentation
=============

We recommend that you read the section: [Build with PyBossa](http://docs.pybossa.com/en/latest/build_with_pybossa.html) and follow the [step by step tutorial](http://docs.pybossa.com/en/latest/user/tutorial.html).


Adding pictures from a folder in an S3 bucket
=============================================

This application supports public S3 buckets. Adding pictures/photos from
a folder in a S3 bucket is as simple as running the following commands.

```bash
    $ python createTasks.py -s server -k api-key -c -x -b "folder/in/s3/"
```
To add all images in the root folder run:

```bash
    $ python createTasks.py -s server -k api-key -c -x -b "/"
```
To add all images in a subfolder:
```bash
    $ python createTasks.py -s server -k api-key -c -x -b "micropasts-olduvai"
```

If the application had already some tasks, the previous command will add
pictures in the S3 folder to the app, so you can easily add more tasks when
they are completed in your PyBossa application.

By default this application only supports PNG and JPG pictures, but you can add
more extensions if you want by editing the s3_settings.py

**NOTE**: This application uses the [pybossa-client](https://pypi.python.org/pypi/pybossa-client) in order to simplify the development of the application and its usage. Check the [documentation](http://pythonhosted.org/pybossa-client/).


LICENSE
=======

Please, see the COPYING file.
