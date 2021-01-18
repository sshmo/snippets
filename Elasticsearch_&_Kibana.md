# Elasticsearch installation and setup
    
    # use vpn
    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.10.1-amd64.deb
    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.10.1-amd64.deb.sha512
    shasum -a 512 -c elasticsearch-7.10.1-amd64.deb.sha512 
    sudo dpkg -i elasticsearch-7.10.1-amd64.deb
    
    sudo update-rc.d elasticsearch defaults 95 10
    sudo -i service elasticsearch start
    sudo -i service elasticsearch stop
    
# Kibana installation and setup    
    
    # use vpn
    wget https://artifacts.elastic.co/downloads/kibana/kibana-7.10.2-amd64.deb
    shasum -a 512 kibana-7.10.2-amd64.deb 
    sudo dpkg -i kibana-7.10.2-amd64.deb
    
    sudo update-rc.d kibana defaults 95 10
    sudo -i service kibana start
    sudo -i service kibana stop

# To delete an index in Elasticsearch:

    curl -XDELETE localhost:9200/<index name>
    
    # Using elasticsearch module
    from elasticsearch import Elasticsearch
    es = Elasticsearch()
    es.indices.delete(index='test-index', ignore=[400, 404])
