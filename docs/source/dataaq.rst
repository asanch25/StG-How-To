Data Retrieval
==============






stgdaq
--------------------------


Backing up .evt files
---------------------

.. note::
    Do NOT back up the evt files for an experiment in your own personal space. It belongs in the groupspace where it is easily accessible.


Converting .evt files to ROOT files
-----------------------------------
The next step is to convert the evt files we just backed up to root files within the directory you wish to work in. There are various versions of a program called evt2root floating around, so the best way to get a hold of it as of right now is to look in the user space of another grad student to copy that into the directory you are doing your work in. At some point there will be a unified evt2root version that is easily accessible but that hasn't happened yet. As the name implies, evt2root converts .evt files to .root files that can be analyzed using CERN's ROOT framework. The other file you need to get your hands on (or copy the example that will show up in a second) is :code:`convert.sh` which is a bash script that will use evt2root to convert all the .evt files you just backed up. This particular example of :code:`convert.sh` is what I used to convert some Si detector calibration data, but it is easy to modify to convert any data you want. 

:code:`convert.sh`

.. code-block:: console

    #!/usr/bin/env bash

    # Variables for directories and command

    #Specify the directory the .evt files for this particular experiment are backed up to
    input_directory="/afs/crc.nd.edu/group/nsl/rms/exp/2024_06_11_Si_calibration"

    #Specify the evt2root directory that you are using
    conversion_command="/afs/crc.nd.edu/group/nsl/rms/user/asanch25/data-analysis/Calibrations/2024_06_11_Si_calibration/evt2root/exec/evt2root"

    #need to remove the end of the .evt file name
    suffix_to_remove="-13328.evt"
    
    # Loop over each .evt file in the input directory
    for evt_file_path in "${input_directory}"/*.evt; do
    
        # Print the full path of the current .evt file
        echo "${evt_file_path}"
        
        # Extract the filename from the full path
        file_name=$(basename -- "${evt_file_path}")
        echo "${file_name}"
        
        # Remove the specified suffix from the filename
        file_name_without_extension="${file_name%${suffix_to_remove}}"
        echo "${file_name_without_extension}"
    
        # Run the conversion command with the output and input file paths
        "${conversion_command}" \
            -o \
            "${file_name_without_extension}.root" \
            "${evt_file_path}"
    
    done

.. note:: 
    This will create the .root files in whatever directory :code:`convert.sh` is in.

You cannot run this script just yet, and I recommend creating a folder named something like :code:`root_binaries` and moving the script in there for later. Your file structure should look something like this as of right now,

::

    Experiment
    ├── evt2root         
    │   ├── evt2root stuffs
    ├── root_binaries         
    │   ├── convert.sh

Now we need to actually compile evt2root in this directory so that you can run the conversion script. Assuming you are starting from the :code:`Experiment` directory, you first want to enter the evt2root directory,

.. code-block:: console

    cd evt2root

Next you want to remove the build directory,

.. note::
    The -r in the remove command is for recursive and will delete EVERYTHING in the build directory. Be careful using that command. 

.. code-block:: console

    rm -r build

Remake the build directory and enter it

.. code-block:: console

    mkdir build
    cd build

Then you need to load the cmake module
    
.. code-block:: console

    module load cmake

And finally let cmake do its thing

.. code-block:: console

    cmake ..
    cmake install


After running these commands in the terminal within the evt2root directory, evt2root should be ready. For the next step you need to :code:`module load root` the latest version of root. :code:`cd ..` out of the evt2root directory and go into the :code:`root_binaries` directory where you have the :code:`convert.sh` script. Once you are there,

.. code-block:: console

    ./convert.sh

Should well...convert all the .evt files you specified to to .root files that will be created in the :code:`root_binaries` directory you created.


Automagically load modules on the CRC
-------------------------------------
If you get tired of manually loading ROOT or some other module, there is a way to have the crc automatically do this on login. Immediately when you log into a crc computer, where you have your :code:`Private` :code:`Public` :code:`www` and :code:`YESTERDAY` directories, there is a hidden file :code:`.bashrc`. Open this in your text editor of choice and you should see something like this:

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

