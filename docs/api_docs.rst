
************************************************
General
************************************************

Introduction
================================================

One of Marine Benchmark core services is to deliver data B2B via a robust API service. The service consists of both a generic data catalogue based service and bespoke calls as per agreement. 

The technology behind the API is a REST API written in Node and consists of multiple servers and a multiple services architecture ready to serve client calls. 

The API consists of two general API call types, Bespoke API and Generic API. Bespoke API is based on a client customized call structure. Generic API is a default large set of calls from our standard catalogues


Purpose and Scope
================================================

Bespoke data API is custom calls created for detailed information per customer. Technically it is a custom defined dataset that can be retrieved via API in formats and mean of delivery stated below. Please see abovefor what arguments are valid for bespoke calls.

PlatformThe web services allow access to Marine Intelligence supplied by Marine Benchmark while keeping the data secured for authorized users.This document provides information about the technical features of the API, and describes its parameters formats and other details.


Revision History
================================================


* June 2021 - 1.4.1
    * Ported to web and updated resources
* April 2021 - 1.4
    * Updating resources and examples for API v4
* February 2021 - 1.3
    * Updating appendix adding arguments and configurator reference
* June2020 - 1.2
    * Updating appendix etc.
* Nov 2019 - 1.1
    * Document creation




API Access
================================================



API URL
------------------------

The API can be accessed from the following URL. Beside an URL, a ``catalogue code`` and ``arguments`` as per below are needed.

::

    https://apigateway.marinebenchmark.com/{API_CALL CODE}<URL-arguments/parameters>


API Authentication
------------------------

Marine Benchmark API hosts two ways of authentication, simple and extended.


* Simple authentication is a combination of a key based authentication via a URL argument and an IP number white list requirement. The procedure is, you provide your public calling server IP and we provide it to our authentication system. You will also be provided with a API key to be added to the URL: For example: ``key=kd48!kf%3kFmsaRy!qe``

* Extended API authentication is a ticket-based login without need for a white list of the IP number. Though it might require some work on the API client side. Please contact our development team for more details.


Language and Time Encoding
================================================

When using special characters or spaces in URL, they must be URL encoded.

+------------------------+-------------------+
| Hourly (1HR or 6HR)    | ``YYYYMMDDHH``    |
+------------------------+-------------------+
| Daily (DAY)            | ``YYYYMMDD``      |
+------------------------+-------------------+
| Weekly (WEK)           | ``YYYYWW``        |
+------------------------+-------------------+
| Monthly (MON)          | ``YYYYMM``        |
+------------------------+-------------------+
| Quarterly (QTR)        | ``YYYYQ``         |
+------------------------+-------------------+
| Yearly (YER)           | ``YYYY``          |
+------------------------+-------------------+

Resources 
================================================



Resource Information
------------------------


.. list-table:: Resource information
   :widths: 50 50
   :header-rows: 0

   * - Response formats
     - ``JSON``, ``XML``, ``CSV``, ``Compact``
   * - Response delivery
     - ``String``, ``file``
   * - Requires authentication?
     - ``Yes``



URL Parameters
------------------------

.. list-table:: URL parameters
    :widths: 15 15 40 15 15
    :width: 100%
    :header-rows: 1
    :class: tight-table, url-table


    * - Parameter
      - Required
      - Description
      - Default Value
      - Example value
    * - ``key``
      - **required**
      - Credential. An API key is required for every request. 19 characters long (for simple authentication mode).
      - 
      - ``kd48!kf%3kFmsaRy!qe``
    * - ``condition``
      - **required**
      - Sets the condition in SQL format. Typically period and an Entity. Also supports multiple entities by comma separation.
      -
      - Period between **202001** and **202106** and **Entity1ID** in (**9236315**)
    * - ``measure``
      - **required**
      - Sets the requested measure(s). Multiple measure can be requested by a comma-separation. Aggregate conditions can also be specified but requires the aggregate parameter to be set.
      - 
      - - ``SPEDMVLO``  -    *Speed moving loaded* 
        - ``SPEDMVLO, TOFUMVLO, TOFUMVUL``   -   *Speed moving loaded, Total fuel moving loaded, Total fuel moving unloaded*
    * - ``aggregate``
      - *optional*
      - Sets the aggregate by clause.
      - 
      - ``period``
    * - ``sort``
      - *optional*
      - Sets the dimension to sort by.  Sort should be used with care as it can, on the margin, delay answer. Available options are ``Period``, ``Entity1ID``, ``Value`` (depending on labelType), ``Area1ID`` and more.. Ascending or descending order can also be specified. 
      - ``Period``
      - - ``Period asc`` 
        - ``Value desc``
    * - ``labelType``
      - *optional*
      - Sets the label type for the json response.
      - ``0``
      - - ``0`` - Unified
        - ``1`` - Code   
        - ``2`` - Name  
    * - ``periodCorrected``
      - *optional*
      - Corrects month to a normalized month. Normalized month consists of 30.45 days. NB good for compare in graphs but presents skewed values for each individual month.
      - ``0``
      - - ``0`` - Unified
        - ``1`` - Code   
        - ``2`` - Name 
    * - ``delivery``
      - *optional*
      - Sets the delivery method. Available methods are ``string`` and ``file``.
      - ``string``
      - ``string`` , ``file``
    * - ``format``
      - *optional*
      - Sets the delivery format. Available formats are ``json``, ``xml``, ``csv`` and ``compact``.
      - ``json``
      - ``csv``, ``xml``, ``csv``, ``compact``    

.. Note::
   Please note than parameter values **must** be URL encoded. 
   ``condition=Period%20between%20202001%20and%20202106%20and%20Entity1ID%20in%20(9236315)``

 

Example Requests
------------------------

URL: ``https://apigateway.marinebenchmark.com/V4/{API_CATALOGUE_CODE}<URL-parameters>``

Method: **GET**

Example request: :: 

    https://apigateway.marinebenchmark.com/V4/MBVESGLOWEK?key=xxxxxxxxxxx&condition=Period%20between%20202001%20and%20202003%20and%20Entity1ID%20in%20(9236315)&measure=SPEDSTTO&sort=Period&labelType=0&periodCorrected=0&delivery=string&format=json 


Example Response
------------------------

.. code-block:: json

    [
        [
            {
            "TimeSerieCatalogueCode": "MBVESGLOWEK",
            "TimeSerieName": "Vessel Global Weekly - Speed steaming total",
            "StatisticsCatalogueDescription": "Here we will add user descriptions for statistics catalogue",
            "MeasurementDescription": "speed steaming total in period. Steaming is all speed with a speed above 6 knots. Total is speed independent of loaded or unloaded.",
            "TimeSerieUnit": "kn",
            "TimeSerieMeasureCode": "SPEDSTTO"
            }
        ],
        [
            {
            "Entity1ID": 9236315,
            "Period": 202001,
            "Area1ID": 0,
            "Area2ID": 0,
            "Value": 7.988872576
            },
            {
            "Entity1ID": 9236315,
            "Period": 202002,
            "Area1ID": 0,
            "Area2ID": 0,
            "Value": 8.80499174
            },
            {
            "Entity1ID": 9236315,
            "Period": 202003,
            "Area1ID": 0,
            "Area2ID": 0,
            "Value": 7.892691355
            }
        ]
    ]
