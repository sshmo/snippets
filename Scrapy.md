# Installation notes & initial setup
    
    # Don’t use the python-scrapy package provided by Ubuntu, they are typically too old and slow to catch up with latest Scrapy.
    
    sudo apt-get install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev
    pip install scrapy
    
    scrapy startproject <name> .
