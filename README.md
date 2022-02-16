# Online Barcode Reader with Django
The sample demonstrates how to create an online Barcode Reader with Django, [Dynamic Web TWAIN SDK](https://www.dynamsoft.com/web-twain/overview/) and [Dynamsoft Barcode Reader SDK](https://www.dynamsoft.com/barcode-reader/overview/).

## About Dynamic Web TWAIN

- [![](https://img.shields.io/badge/Get-30--day%20FREE%20Trial%20License-blue)](https://www.dynamsoft.com/customer/license/trialLicense/?product=dwt)

## About Dynamsoft Barcode Reader

- [![](https://img.shields.io/badge/Get-30--day%20FREE%20Trial%20License-blue)](https://www.dynamsoft.com/customer/license/trialLicense/?product=dbr)


## Python Development Environment

- Python 3.7.9

    ```bash
    python --version
    ```

- Django 3.2.7
    
    ```bash
    python -m pip install Django
    python -m django --version
    ```

## Usage
1. Install Dynamsoft Barcode Reader
    
    ```bash
    pip install dbr
    ```
2. Set license keys for Dynamic Web TWAIN and Dynamsoft Barcode Reader.

    Go to file 'static/dwt/Resources/dynamsoft.webtwain.config.js', change the product key:
    
    ```js
    Dynamsoft.DWT.ProductKey = 'DWT-KEY';
    ```
    Go to file /dwt/views.py, change the product key:
    ```python
    reader.init_license("DBR-KEY")
    ```

3. Run the project:

    ```bash
    python manage.py makemigrations
    python manage.py migrate --run-syncdb
    python manage.py runserver
    ``` 
    
4. visit `127.0.0.1:8000` in a web browser.

    ![load_multi_barcode](https://www.codepool.biz/wp-content/uploads/2015/07/load_multi_barcode.png)

    ![barcode_results](https://www.codepool.biz/wp-content/uploads/2015/07/barcode_results.png)

## Blog
[How to Build Online Barcode Scanning App with Python Django](https://www.dynamsoft.com/codepool/django-barcode-scanning-app.html)



