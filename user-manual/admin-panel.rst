.. role:: admin_ui_button(strong)

************************
Admin Software Functions
************************

To open the admin pannel please visit ``http://<ip_of_mint_server>/`` in your 
web browser and login with your administrator password. The default administrator
password is ``admin``. Please make sure to change the default value after
installation.

---------------
The project tab
---------------

^^^^^^^^^^^^^^^^
Delete a Project
^^^^^^^^^^^^^^^^

Select the project you want to delete and click the :admin_ui_button:`DELETE` button. 
You will be asked to confirm the deletion. If you are sure to delete 
the project confirm this question with :admin_ui_button:`YES` or press :admin_ui_button:`CANCEL` if not. 
If you delete a project, Mint will only delete the project and media files 
from this particular project but not from its sub projects or parent projects. 

^^^^^^^^^^^^^^^
Close a project
^^^^^^^^^^^^^^^

In order to close a project remotely use this function. Make sure that you tell
the editor before you do so.

^^^^^^^^^^^^^^^^^^^^^
Force close a project
^^^^^^^^^^^^^^^^^^^^^

If for any reason it is not possible to close a project on the client 
computer (e.g. OS or power supply failure) you can force close this project 
from the Mint admin panel by selecting the project and clicking :admin_ui_button:`FORCE CLOSE`. 
Please never force close projects that are actively opened by an editor! 
The editor could lose unsaved progress and will experience *media offline* issues.

------------------
Managing Templates
------------------

Mint allows you to create templates for all kind of editing projects. 
These templates can contain custom files and folder structure.
Once a template is created, it can be chosen by the editor upon project
creation. 

^^^^^^^^^^^^^^^^^^^
Creating a template
^^^^^^^^^^^^^^^^^^^

In order to create a template, click on the :admin_ui_button:`TEMPLATES` tab in the admin panel
and then the :admin_ui_button:`CREATE NEW` button. You will see a shadow box asking for a template
name, a template preset, and a substitution token & pattern. The presets are
optimized for certain editing applications.

generic
  Use this preset for templates which will not be Avid or Adobe related.

avid
  Use this preset for editing applications of the Avid product family.

adobe
  Use this preset for Adobe Premiere and Adobe After Effects.

The substitution token is a string that will be replaced by the substition pattern 
in file and directory names contained in the project template. The substitution
pattern defines how the project name will be constructed upon project
attributes. Aside from any generic string, you may enter date-related
placeholders such as *%Y* (two-digit year), *%m* (month), and *%d* (day). The
variables follow the conventions of the standard Unix tool
`date <http://unixhelp.ed.ac.uk/CGI/man-cgi?date>`_. Furthermore, the
placeholder *%{name}* will be replaced by the name of the project.

For example, if the template contained a Avid project called *replace_me_1080i.avp*, 
and the subsitution token was *%Y%m%d-%{name}*, the file may be named
*130101-projectname_1080i.avp* in a newly created project.

Once you feel confident that the template matches your requirements click
:admin_ui_button:`CREATE`. The job is not exactly done now. Point your file browser to the
*templates/* directory on the storage and navigate to the newly created
template's directory. You will see a folder *project* and a folder for each of
your media storages. You may create custom file and folder structures inside
these directories. 

For example, if you already created an Avid template in the Mint admin panel,
create a new Avid project called *replace_me* in the Avid editing application, 
configure it to your requirements and copy the corresponding *.avp*, *.avs*, and *.xml*
file to the template directory on the storage.

-----------------------
Miscellaneous Functions
-----------------------

^^^^^^^^^^^^^^^^^^^^^^^^^
Change the admin password
^^^^^^^^^^^^^^^^^^^^^^^^^

You may change the admin password here, by enterring the current password and
the new password. It is a good idea to change the password once the Mint
backend is set up. The standard password is *admin*. If you lost your password,
please contact *support@flavoursys.com* for further instructions.

---------------
The License Tab
---------------

After you purchased a license, you will get a license key that you paste in the
*Upload license* field. Click :admin_ui_button:`UPDATE` to confirm and restart the Mint backend.
No editing system should be continue while updating the license.
