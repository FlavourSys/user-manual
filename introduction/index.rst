.. _index_introduction:

############
Introduction
############

Mint is a software-only product by FlavourSys that was created for small to 
medium sized video post productions. Mint enables project sharing for Avid©,
Adobe and Final Cut editing projects and can be easily installed on most
Unix/Linux based NAS or SAN systems, optimizing them for collaborative video
editing, including all the benefits of secure project sharing and bin/project
locking.

*******************
System Requirements
*******************

Mint requires the following minimum software configuration:

:Mint Server: Recent Linux distributions (Kernel 2.6.32 or higher, Ruby 1.9 and higher, GCC, MySQL 
  database), recent BSD derivatives (e.g., FreeBSD 9.0 or higher, with Ruby, MySQL, 
  and a C compiler included)
:Mint Client: Windows 7 or higher, Mac OS X 10.6 (Snow Leopard) or higher, recent Linux 
  distributions

The Mint Server runs on many popular SAN MDCs (Metadata Controllers), but can also 
run on a dedicated host which has file access to the storage. The Mint Server only 
has humble expectations with regards to the hardware features of such a machine, 
however, the performance will vary greatly depending on how many files your average 
editing project may have.

****************
Supported Setups
****************

.. todo:: explicitly name SAN types (StorNext, HyperFS)

==========  ============  ==================
Client OS   Storage Type  Network Connection
==========  ============  ==================
MS Windows  NAS           CIFS/SMB
MS Windows  SAN           (SAN manufacturer)
Mac OS X    NAS           CIFS/SMB + NFS
Mac OS X    NAS           Dave [#dave]_
Mac OS X    SAN           (SAN manufacturer)
==========  ============  ==================

Please note that using Mac OS X and SAN, the Mint Client needs administrator privileges 
in order to create virtual volumes. For this purpose, it will ask the user to provide
his password on its first run after each reboot of the host machine.

.. [#dave] http://www.thursby.com/products/dave.html
