Data Retrieval
==============
.. _whatis:

stgdaq
--------------------------


Backing up .evt files
---------------------

.. note::
    Do NOT back up the evt files for an experiment in your own personal space. It belongs in the groupspace where it is easily accessible.


Converting .evt files to ROOT files
-----------------------------------
The next step is to convert the evt files we just backed up to root files within the directory you wish to work in. 


Automagically load modules on the CRC
-------------------------------------
If you get tired of manually loading ROOT or some other module, there is a way to have the crc automatically do this on login. Immediately when you log into a crc computer, where you have your Private Public www and YESTERDAY directories, there is a hidden file .bashrc. Open this in your text editor of choice and you should see something like this:

.. code-block:: console

    #Check http://crc.nd.edu/wiki for login problems
    #Contact crcsupport@nd.edu if further problems

    if [ -r /opt/crc/Modules/current/init/bash ]; then
        source /opt/crc/Modules/current/init/bash
    fi

    # Source global definitions
    if [ -f /etc/bashrc ]; then
            . /etc/bashrc
    fi

    #Additional aliases

    #Additional modules

    ~
If you want some extra functionality, we can add some extra snippets of command language. We can create :code:`#Additional aliases` that will let you access directories on the crc much more easily. It lets you essentially create commands that you can enter into the terminal to immediately take you to a directory, regardless of where you are at in the file system. For example, this is what I have under :code:`#Additional aliases`

.. code-block:: console

    #Additional aliases
    alias groupspace='cd /afs/crc.nd.edu/group/nsl/rms'
    alias adam='cd /afs/crc.nd.edu/group/nsl/rms/user/asanch25'
    alias currentexp='cd /afs/crc.nd.edu/group/nsl/rms/user/asanch25/data-analysis/Experiments/2023_07_22_15N_aa'

As you can see I have a terminal command that will take me to the RMS groupspace, my own user folder within that space, as well as a command to directly take me to my current experiment analysis folder. 

Another useful feature is to have the CRC automatically load modules for you on login. You will need to pay attention to CRC upgrades for whether or not these modules actually exist and still remain funcitonal, but it is just as easy to stop them from loading on login. For example here is what I have under :code:`#Additional modules.`

.. code-block:: console

    #Additional modules
    module use -a /afs/crc.nd.edu/user/n/nsl/nuclear/x86_64_linux_el6/nsl_modules #uncomment this after crc upgrade nonsense has been sorted out
    #module load geant/4.10.5_mt root/6.24.06  qt/4.8.7 cmake
    #module load root/6.26.10 #uncomment this after crc upgrade nonsense has been sorted out

With these commands I am loading the NSL modules, but I have commented out the loading of some other modules because of a recent CRC upgrade. If you are ever in doubt of what versions of a specific module are available on the CRC, the command :code:`module avail <modulename>` will show you a list of available versions.

