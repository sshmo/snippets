# Installation and setup

    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.10.1-amd64.deb
    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.10.1-amd64.deb.sha512
    shasum -a 512 -c elasticsearch-7.10.1-amd64.deb.sha512 
    sudo dpkg -i elasticsearch-7.10.1-amd64.deb
    
    sudo update-rc.d elasticsearch defaults 95 10
    sudo -i service elasticsearch start
    sudo -i service elasticsearch stop

# To delete an index:

    curl -XDELETE localhost:9200/<index name>
