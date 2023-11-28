Role Name
=========

This role is to install **Matlab** in managed host(s).

Prerequisite
------------

The following three files needs to be available on a NFS file system that is auto-mounted via AUTOFS:
- installation options file that is made up of all options paramenters for the installation, 
- Matlab ISO file downloaded from MathWorks, 
- and a network license file that contains the information about license server, such as IP address and port number.

Default locations of the files are in **defaults/main.yml** file.

Role Variables
--------------

1. **matlab_ini** - location of installation options file. File installation key (FIK) is for Matlab installation, and LicensePath is the location of network license file which contains netwok license server to run Matlab.
1. **matlab_iso** - location of Matlab ISO image file
1. **successful_install** - the last word in installation log file when Matlab-runtime is installed successfully. The location of the installation log file is defined in **matlab_ini**

Default values for these variables are in **defaults/main.yml** file.

Dependencies
------------

None.

Example Playbook
----------------

As an example of how to use this role, the **tests/test.yml** is the good place to check.

    - hosts: servers
      roles:
         - software-matlab
