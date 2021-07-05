
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
| Weekly (WEK)           | ``CYYYYWW``       |
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

Response formats
JSON, XML, CSV, Compact
Response delivery
String, file
Requires authentication?
Yes

.. list-table:: 
   :widths: 25 25 
   :header-rows: 0

   * - Response formats
     - ``JSON``, ``XML``, ``CSV``, ``Compact``
   * - Response delivery
     - ``String``, ``file``
   * - Requires authentication?
     - ``Yes``




URL Parameters
------------------------


Example Requests
------------------------

Example Response
------------------------



************************************************
Bespoke API
************************************************

Bespoke data API is custom calls created for detailed information per customer. Technically it is a custom defined dataset that can be retrieved via API in formats and mean of delivery stated below. Please see abovefor what arguments are valid for bespoke calls.

If you are interested in custom designed calls please contact Marine Benchmark sales or development to iron out content and layout


************************************************
Generic API
************************************************