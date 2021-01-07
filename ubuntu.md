# Boot repair

    sudo add-apt-repository ppa:yannubuntu/boot-repair
    sudo apt-get update
    sudo apt-get install -y boot-repair && boot-repair

# update us.archive to ir.archive

    sudo nano /etc/apt/sources.list
    ^ == cnrl
# The following signatures couldn't be verified because the public key is not available: NO_PUBKEY <THE KEY>

    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys <THE KEY>
