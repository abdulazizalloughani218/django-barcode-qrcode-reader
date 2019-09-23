# Online Barcode Reader with Django
The sample demonstrate how to create an online Barcode Reader with Django, Dynamic Web TWAIN SDK and Dynamsoft Barcode Reader SDK.

Download & Installation
-----------------------
* [Django][1]
* [Dynamic Web TWAIN SDK][2]
* [Dynamsoft Barcode Reader SDK][3]

How to Create an Online Barcode Reader in Python
-----------
1. Create a new Django project with the [basic steps][4].
2. Create a simple Python Barcode Reader with the [sample code][5].
3. Copy Python Barcode Reader to ``{Django Project Root}\dwtupload``.

    ![copy_python_barcode](http://www.codepool.biz/wp-content/uploads/2015/07/copy_python_barcode.png)
    
4. Create a Python module `dbr.py`.

    ```Python
    import os.path
    from dbr import DynamsoftBarcodeReader
    dbr = DynamsoftBarcodeReader()

    def decodeFile(fileName):
        if not os.path.isfile(fileName):
            print "It is not a valid file."
            return

        results = dbr.decodeFile(fileName, config.barcodeTypes)
        json = {}
        tmp = []
        i = 0

        # Convert results to JSON
        for result in results:
            key = formats[result[0]]
            value = result[1]
            tmp = [key, value]
            json[i] = tmp
            i += 1;

        return str(json)

    ```

5. Import the module to `views.py`.
6. Detect the uploaded Barcode image files and return results to Web client.

    ![load_multi_barcode](http://www.codepool.biz/wp-content/uploads/2015/07/load_multi_barcode.png)
    ![barcode_results](http://www.codepool.biz/wp-content/uploads/2015/07/barcode_results.png)

Blog
----
[Reading Barcode from Scanned Documents][6]

[1]:https://www.djangoproject.com/download/
[2]:http://www.dynamsoft.com/Downloads/WebTWAIN_Download.aspx
[3]:http://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Download.aspx
[4]:https://github.com/dynamsoftsamples/dwt-django-file-upload#basic-steps
[5]:https://github.com/dynamsoft-dbr/python
[6]:http://www.codepool.biz/read-barcode-from-documents.html
