Data Retrieval
==============
.. _whatis:

stgdaq
--------------------------

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
If you want some extra functionality, we can add some extra snippets of command language. We can create :code:`#Additional aliases.` that will let you access directories on the crc much more easily. It lets you essential create commands that you can enter into the terminal to immediately take you to a directory, regardless of where you are at in the file system. For example, this is what I have under :code:`#Additional aliases.`

.. code-block:: console
    #Additional aliases
    alias groupspace='cd /afs/crc.nd.edu/group/nsl/rms'
    alias adam='cd /afs/crc.nd.edu/group/nsl/rms/user/asanch25'
    alias currentexp='cd /afs/crc.nd.edu/group/nsl/rms/user/asanch25/data-analysis/Experiments/2023_07_22_15N_aa'




    #Additional modules
    module use -a /afs/crc.nd.edu/user/n/nsl/nuclear/x86_64_linux_el6/nsl_modules #uncomment this after crc upgrade nonsense has been sorted out
    #module load geant/4.10.5_mt root/6.24.06  qt/4.8.7 cmake

    #module load root/6.26.10 #uncomment this after crc upgrade nonsense has been sorted out



