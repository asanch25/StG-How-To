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
The next step is to convert the evt files we just backed up to root files within the directory you wish to work in. There are various versions of a program called evt2root floating around, so the best way to get a hold of it as of right now is to look in the user space of another grad student to copy that into the directory you are doing your work in. At some point there will be a unified evt2root version that is easily accessible but that hasn't happened yet. As the name implies, evt2root converts .evt files to .root files that can be analyzed using CERN's ROOT framework. Once the evt2root folder has been copied into your working directory the following steps will prepare it for the conversion of the .evt files you just backed up. I am assuming you have some file structure like this:

::

    Experiment
    ├── evt2root         
    │   ├── evt2root stuffs
    ├── root_binaries         
    │   ├── convert.sh
    

.. code-block:: console

    #remove the build directory
    rm -r build

    #create a new build directory
    mkdir build

    #load cmake
    module load cmake

    #go into the build directory
    cd buildl
    
    #let cmake do its thing
    cmake ..
    cmake install

After running these commands in the terminal within the evt2root directory, evt2root should be ready. For the next step you need to :code:`module load root` the latest version of root. :code:`cd ..` out of the evt2root directory and do the following:

.. code-block:: console

    #create a directory for your root files
    mkdir root_binaries

Once you have created the directory you wish to store your root files in, the next step is to use the conversion script :code:`convert.sh` to... well convert all the evt files you have in your experiment directory to root files in your root_binaries directory. 


:code:`convert.sh`:

.. code-block:: console

    #!/usr/bin/env bash

    for evt_file_path in /afs/crc.nd.edu/group/nsl/rms/exp/2024_06_11_Si_calibration/*.evt; do
    
        echo ${evt_file_path}
        file_name=$(basename -- "${evt_file_path}")
        echo ${file_name}
        file_name_without_extension="${file_name%-13328.evt}"
        echo ${file_name_without_extension}
    
        /afs/crc.nd.edu/group/nsl/rms/user/asanch25/data-analysis/Calibrations/2024_06_11_Si_calibration/evt2root/exec/evt2root \
            -o \
            ${file_name_without_extension}.root \
            /afs/crc.nd.edu/group/nsl/rms/user/asanch25/data-analysis/Calibrations/2024_06_11_Si_calibration/evt_files/${file_name}
    
    done








EVT to ROOT:
Create run folder in data analysis.
Copy the evt_files get-evtfiles.sh into the working directory. Cp source get-evtfiles.sh
Change the run numbers in that file.
./get-evtfiles.sh to get the evt files from DAQ.
Copy the evt2root folder from previous runs. Cp -R source/* evt2root/
Delete the build directory or create a new build directory in the evt2root.
Module load cmake
Cd build
Cmake ..
Make install
Create root_files directory
Copy the convert.sh from previous runs. Cp source convert.sh
./convert.sh
Root files should be in the root_files.












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

