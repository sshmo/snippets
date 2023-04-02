# Scrapy

## Installation notes & initial setup

``` bash
    # Don’t use the python-scrapy package provided by Ubuntu, they are typically too old and slow to catch up with latest Scrapy.
    sudo apt-get install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev
    pip install scrapy
    
    scrapy startproject <name> .
```

## The main drawback of Scrapy is its inability to natively handle dynamic websites; Use [Selenium with Scrapy](https://github.com/clemfromspace/scrapy-selenium) instead

```bash
    pip install scrapy-selenium
```

``` py
    # Add the following to scrapy settings.py
    from shutil import which
    SELENIUM_DRIVER_NAME = 'firefox'
    SELENIUM_DRIVER_EXECUTABLE_PATH = which('geckodriver')
    SELENIUM_DRIVER_ARGUMENTS=['-headless']  # '--headless' if using chrome instead of firefox
    
    #Add the SeleniumMiddleware to the downloader middlewares:
    DOWNLOADER_MIDDLEWARES = {
        'scrapy_selenium.SeleniumMiddleware': 800
    }
    
    from scrapy_selenium import SeleniumRequest
    yield SeleniumRequest(url=url, callback=self.parse_result)
    
    def parse_result(self, response):
        print(response.selector.xpath('//title/@text'))
```

## Install geckodriver in Ubuntu

Find the [latest version](https://github.com/mozilla/geckodriver/releases) of the driver for your platform and download it. For example:

```bash
    wget https://github.com/mozilla/geckodriver/releases/download/v0.28.0/geckodriver-v0.28.0-linux64.tar.gz
    tar -xvzf geckodriver*
    chmod +x geckodriver
    sudo mv geckodriver /usr/bin/
```
