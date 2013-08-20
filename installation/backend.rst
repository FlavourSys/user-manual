***************************
Installing the Mint backend
***************************

So you decided to install the Mint backend yourself? That's great! Technically, 
the Mint backend can be considered a quite ordinary web application. It is driven by the magnificient
RubyOnRails framework and therefore should run on any recent *GNU/Linux*
distribution as well as other UNIX derivates, such as Apple's *Darwin* and *BSD-based* distributions.
The installation process follows the standard procedure of installing up a
RoR-based web service, i.e., setting up the HTTP daemon, configuring the
database, configuring the web service itself and, last but not least, firing up
the web service (at boot time). Nothing we haven't done before, right?

However, for the sake of convenience we created an installation script which
automates the procedure for the most common systems on which the Mint backend is
likely to be installed. This means both a *common* GNU/Linux server distribution (Red Hat/CentOS
5.x-6.x or Debian 6.x-7.x) and a *fresh* installation, i.e., no preconfigured webserver, no obscure
NicheSQL database and the like. In case you are going to install the Mint backend
on a BSD derivate, or on an Apple Mac OSX system, or on your four-decades-old
mainframe - **which is just perfect** - you may experience some shortcomings of the
installation script. In this case we would kindly ask you to *infer* the necessary installation 
steps on your system from the source code of the very script.
 
=======================
The installation script
=======================

On a common GNU/Linux server system, the Mint installer will perform all the
steps required to convert your bare Linux machine into a fully-fledged, Ruby-running
web server. To start the installation, simply type ``./install.sh`` as root user 
into the command prompt. You will be greeted with the following overview of the installation::

  STATUS:
  ============================================================
  Detect the operating system ...................... [NOT RUN]
  Setup rpmforge repositories ...................... [NOT RUN]
  Configure the nginx repository ................... [NOT RUN]
  Install system packages .......................... [NOT RUN]
  Configure the MySQL database ..................... [NOT RUN]
  Create the installation directories .............. [NOT RUN]
  Install the Ruby interpreter from source ......... [NOT RUN]
  Install the Strawrage storage manager ............ [NOT RUN]
  Install the FsBase application ................... [NOT RUN]

You may then choose between running the installation automatically, running a
single task and exiting the installer. If you decide for the automatic
installation, the installer will try to execute the installation steps
sequentially, in the order they are listed in the overview. When the installer fails 
to perform a certain task, you will be asked if you would like to continue the
installation anyway or would like to abort the installation. Furthermore, the
installation tasks may specify dependencies among each other (for example, the
FsBase installation requires Ruby to be installed), in which case the installer
will ask you a second time whether you really would like to continue.

The installation will require almost no attention from your side, apart from
the *MySQL database configuration* task asking you for a password once. Yet, other
than the Ruby compilation, which may take some minutes dependending on your
hardware, the installation will not take much time in total, so do not walk
away too far.

If something goes wrong during the installation, you may have a look at the logfile
(``install.sh.[date].log``) and, after having fixed the problem, restart the
installation from the point of failure. If any tasks repeatedly fails and you
would like to disable it entirely, simply delete the corresponding script from
the ``tasks/`` directory. We are going to implement a *Skip* feature in the
next installer version, promise.

When the installer has completed all its tasks, you should have a running Mint
backend on your server, using a `Nginx <http://nginx.org/>`_ webserver, a
`Ruby <http://www.ruby-lang.org/>`_ 1.9.3 interpreter, and a 
`MySQL <http://www.mysql.com/>`_ database.
