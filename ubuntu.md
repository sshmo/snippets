# Boot repair

    sudo add-apt-repository ppa:yannubuntu/boot-repair
    sudo apt-get update
    sudo apt-get install -y boot-repair && boot-repair

# update us.archive to ir.archive

    sudo nano /etc/apt/sources.list
    # in  nano ^ == cnrl
    
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
    
# viewing files:
    file <filename> # shows the type
    cat <filename> # shows the whole file in on place
    more <filename> # shows the file page by page
    less <filename> # shows the file page by page
    head <filename> # shows first -<number> lines 
    tail <filename> # shows last -<number> lines

# to all processes with detail information:

The state of the process (S): 
O = running on processor
S = sleeping
R = runnable, waiting to run
Z = zombie, process terminated but parent not available
T = process stopped

The state of the process (STAT): 
<: The process is running at high priority.
N: The process is running at low priority.
L: The process has pages locked in memory.
s: The process is a session leader.
l: The process is multithreaded.
+: The process is running in the foreground.

    ps -ef --forest
    ps l --forest
    
