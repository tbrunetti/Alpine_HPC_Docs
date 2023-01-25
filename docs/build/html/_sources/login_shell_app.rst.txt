Logging into Alpine from the Shell App
=======================================

.. note::
    Make sure you already have your XSEDE/ACCESS user name and password set up before proceeding and Duo 2-factor authentication set up for your ACCESS/XSEDE account

1.  Visit https://ondemand-rmacc.rc.colorado.edu. You will be redirected to CILogon.  From there, make sure you select the ACCESS CI (XSEDE) as your identity provider and then click the "Log On" button.   

.. image:: images/ciLogon.png
   :width: 1000


2.  This will take you to the ACCESS CI Logon site.  Input your ACCESS/XSEDE username and password.  Then press the "Login" button:

.. image:: images/access.png
   :width: 1000

3.  You will get a Duo push on your phone to confirm your identity.  Be sure to accept the Duo push.  

.. image:: images/duo.png
   :width: 800

4.  Once confirmed, you will be redirected to the Open OnDemand Research Computing Dashboard site hosted by the University of Colorado Boulder.  At the very top click on the "Clusters" drop down menu and select ">_Alpine Shell".

.. image:: images/shellApp.png
   :width: 800

5.  Once you click that, you will be logged into the head node of the Alpine HPC.  At this point you are in your $HOME directory.  To install packages and transfer scripts, please go to your project directory, located at /projects/yourUsername. 

.. image:: images/alpineTerminal.png
   :width: 800