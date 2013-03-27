.. FlavourSys Strawberry documentation integrator installation (v3),
   created by Mick on 25.02.2013 18:01
.. _integrator_installation:

#######################
Integrator Installation
#######################

************************
Installation preparation
************************
In order to install |product| Server |version| you need the following files:

* ``integrator_install.sh``: `The install script <http://www.piturtle.com/licenses/integrator_install.sh>`_
* ``install_VERSION.img``: `The install image (currently: v3.60) <http://www.piturtle.com/licenses/install_360.img>`_, where "VERSION" needs to be replaced with the actual version number--e. g. ``install_360.img`` for the version 3.60
* ``mysql.tar``: `The default database file <http://www.piturtle.com/licenses/mysql.tar>`_ (as tar archive)
* ``INTEGRATORABBREVIATION_vmVMVERSION.tar``: the actual VM (where "INTEGRATORABBREVIATION" is the short form of the integrator and "VMVERSION" needs to be replaced with the current version number--e. g. `the DVS VM image (v1.4) <http://www.piturtle.com/licdevdown/dvs/dvs_vm1.4.tar>`_)
* *Optional:* ``OSVERSION_rpms.zip``: () the collection of RPMs (required software packages) regarding your OS version ("OSVERSION" needs to be replaced with the actual version number--e. g. ``6.2_rpms.zip`` for CentOS/RHEL version 6.2). The following is a collection of CentOS RPMs regarding the OS version:
    - `CentOS 5.3 <http://www.piturtle.com/licenses/5.3_rpms.zip>`_
    - `CentOS 5.6 <http://www.piturtle.com/licenses/5.6_rpms.zip>`_
    - `CentOS 6.2 <http://www.piturtle.com/licenses/6.2_rpms.zip>`_


.. note:: Check if yum is working, with ``yum install dialog``.  Check if Internet access is working, e. g. with ``mtr -t 8.8.8.8`` or with ``traceroute www.google.com``.

.. code-block:: console

    [root@localhost strawberryext]# ls -lhAF
    total 3.8G
    -rwxr-xr-x 1 root root 3.8G Mar  7 07:55 dvs_vm1.4.tar*
    -rwxr-xr-x 1 root root  68K Mar  6 20:06 install_360.img*
    -rwxr-xr-x 1 root root 9.9K Mar  6 20:06 integrator_install.sh*
    -rwxr-xr-x 1 root root  21M Mar  6 20:08 mysql.tar*
    [root@localhost strawberryext]#


*********
Procedure
*********

Connect to the machine where you would like to install the |product| Server and gain *root* access (either through ``sudo`` or ``su``). After that, type the following in the command prompt:

.. code-block:: bash
    :linenos:

    mkdir /strawberryext
    cd /strawberryext

Download or copy the before mentioned files to the current directory (``/strawberryext``). Enter the following commands:

.. code-block:: bash
    :linenos:

    chmod a+x integrator_install.sh
    ./integrator_install.sh

The following output will be displayed:

.. code-block:: console

             _
           _.\-.__
          /__/\  _/.
         /`. . \| ..\  #####
        |. .. .  . . | #     # ##### #####    ##   #    # #####  ###### #####  #####  #   #
        | ..  . ... .| #         #   #    #  #  #  #    # #    # #      #    # #    #  # #
        \. . .  .. ../  #####    #   #    # #    # #    # #####  #####  #    # #    #   #
         \ . .. . . /        #   #   #####  ###### # ## # #    # #      #####  #####    #
          \. . .. ./   #     #   #   #   #  #    # ##  ## #    # #      #   #  #   #    #
           \ . . ./     #####    #   #    # #    # #    # #####  ###### #    # #    #   #
            `--.-Â´

    RHEL Server Installer Rev. 360

    First run of a DOM Install? (y/n)


**"DOM Install"**: this feature is meant for servers running from a flash based DOM device, which normally does not have enough space to store the virtual machine and database image.

Answering "N" will skip this part, which is recommended for most installs.

Answering "Y" will prompt for a device name, that will be formatted with the *ext3* file-system and bind mounted into the main system. Make sure the device does not contain any important data, as it will be formatted and **all data will be lost**!

.. code-block:: console

    mysql.tar           [  OK  ]


    VM image(s)         [  OK  ]

    Are you ready to install? (y/n)


Answering "N" will stop the execution of the installer to give time to copy all needed files into ``/strawberryext``

Answering "Y" will continue the installation.

.. code-block:: console

    Online install (do not use offline RPMs)? (y/n)

Answering "N" will unpack the RPM files from the included ZIP file and use them for the installation.  Make sure you are using the corresponding package files for your distribution version (e. g. 5.3, 5.6 or 6.3).  These will work with a vanilla install of RHEL or CentOS.

Answering "Y" will give you the following prompt:

.. code-block:: console

    Please enter the Centos/RHEL major version (5 or 6): 6
    Please enter the Centos/RHEL minor version (1 or 2,3,4,5,6,7,8 ): 3
    Add Centos repo (will allow unregistered RHEL to get RPMs online)? (y/n) n


"N" will make the installer use your RHEL subscription or existing CentOS repos to install the needed RPM packages.

"Y" will add the corresponding public CentOS repository.  This will also work with a RHEL installation without subscription. Answer the following questions to define the host systems version:

.. code-block:: console

    Online install ...


.. code-block:: console

    ┌────────────────────────────┐
    │ Number of clients          │
    │ ┌────────────────────────┐ │
    │ │5                       │ │
    │ └────────────────────────┘ │
    │                            │
    │                            │
    ├────────────────────────────┤
    │   <  OK  >  <Cancel>       │
    └────────────────────────────┘







**[tbc.]**
