Docker Image
------------

You can run it directly:

    docker run -p 9001:9001 just4experimental/html-to-pdf
    

Usage
-----

Send a HTTP POST request with the body:

    {
      "content": "base64 encoded html content here",
      "responseContentTypePdf" : false,
      "options": {
        "format": "A4",
        "margin": {
          "top": 10,
          "left": 10
        }
      }
    }
    

Parameters
----------

Key

Type

Description

`content`

string (required)

Any HTML string will do. b64 encoded for easy transport in a json body. Most of the time, you'll get the PDF exactly as you see in your browser. You can use css class and styles in it.

`options`

Puppeteer.[PDFOptions](https://pptr.dev/api/puppeteer.pdfoptions) (optional)

You can pass the options to configure the Puppeteer page

Environment Value
-----------------

Key

Description

`CONCURRENCY`

[puppeteer-cluster concurrency](https://www.npmjs.com/package/puppeteer-cluster#concurrency-implementations) options -> 1:PAGE, 2:CONTEXT, 3:BROWSER. Default: `2`

`MAX_CONCURRENCY`

Max concurrency number. (Max number of tabs/pages). Default: `5`

Links
-----

*   [Github Repository](https://github.com/fluidnotions/html-to-pdf)