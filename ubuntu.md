# Boot repair

    sudo add-apt-repository ppa:yannubuntu/boot-repair
    sudo apt-get update
    sudo apt-get install -y boot-repair && boot-repair
    
# Extend root partition

Change root partition from live usb disk.
You can only add space from adjacent free space.
If swap is in between, delete swap, then extend root then make swap again.

# Recreate swap

Step 1. Format /dev/sda... to be a valid swap 
    
    mkswap /dev/sda...

Step 2. Activate the swap by 

    swapon /dev/sda...

Step 3. modify /etc/fstab to make swap start after every boot.  

    sudo gedit /etc/fstab
    # update UUID received as output of step 1.
    # https://askubuntu.com/a/540167

# update us.archive to ir.archive

    sudo nano /etc/apt/sources.list
    # in  nano ^ == cnrl

# Unable to install “<PACKAGE>”: snap “<PACKAGE>” has “install-snap” change in progress
    
    snap changes
    ...
    123  Doing   2018-04-28T10:40:11Z  -  Install "foo" snap
    ...
    sudo snap abort 123
    snap install foo
    
# The following signatures couldn't be verified because the public key is not available: NO_PUBKEY <THE KEY>

    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys <THE KEY>

# update file with sudo

    sudo getit <filepath>
    
    
# See disk usage detail

open the usage app

# Move a folder
    
    mv source/ target/
    
    # use -i option on cp, mv, rm commands to be asked before overwriting or removing files.

# Show Hidden Files

    ctrl + H

# Custom keyboard shortcuts:
    Keyboard Shortcuts window -> scroll down to reach the + button at thev bottom.

# Find in terminal
    Shift+Ctrl+F

# Having multiple workspaces:
    Super key, then scroll to empty page, start new workspace

# Help on a command:
    man <command>
    
# Viewing files:
    file <filename> # shows the type
    cat <filename> # shows the whole file in on place
    more <filename> # shows the file page by page
    less <filename> # shows the file page by page
    head <filename> # shows first -<number> lines 
    tail <filename> # shows last -<number> lines

# To view all processes with detail information:

    ps -ef --forest

    # The state of the process (S): 
    # O = running on processor
    # S = sleeping
    # R = runnable, waiting to run
    # Z = zombie, process terminated but parent not available
    # T = process stopped
    
    ps l --forest
    
    # The state of the process (STAT): 
    # <: The process is running at high priority.
    # N: The process is running at low priority.
    # L: The process has pages locked in memory.
    # s: The process is a session leader.
    # l: The process is multithreaded.
    # +: The process is running in the foreground.

# Automount File Systems on Linux

    # Step 1: Get the Name, UUID and File System Type
    sudo blkid
    # Step 2: Make a Mount Point For Your Drive
    sudo mkdir /mnt/<name-of-the-drive>
    Step 3: Edit /etc/fstab File
    sudo gedit /etc/fstab 
    #Add UUID=<...>  /mnt/<name-of-the-drive>  ext4  defaults  0  2
    sudo mount -a
