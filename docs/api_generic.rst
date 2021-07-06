************************************************
Generic API
************************************************


API Catalogue Structure
================================================

Datasets are reached by a (typically) 11-characters **catalogue code** with the following structure. Example: ``MBVESGLOWEK``

+--------------+-------------------------------+--------------------------+
| Code         | Full name                     | Specification            |
+==============+===============================+==========================+
| ``MB``       | Marine Benchmark              | Provider                 |
+--------------+-------------------------------+--------------------------+
| ``VES``      | Vessel operational statistics | Category and subcategory |
+--------------+-------------------------------+--------------------------+
| ``GLO``      | Global                        |                          |
+--------------+-------------------------------+    Catalogue             |
| ``WEK``      | Weekly                        |                          |
+--------------+-------------------------------+--------------------------+

The two first letters are always ``MB`` in the generic API, the next 3 charactersspecifies the combination of category and subcategory (``VES``), and the next 6 charactersspecifies catalogue (``GLOWEK – Global weekly``)


API Measurement Structure
================================================

Measurements are specified by a (typically) 8-character **measurement code**. The structure may vary but measurement concerning vessel statistics typically have the following structure.
Example: ``SPEEDSTLO``


.. list-table:: 
    :width: 70%
    :header-rows: 1

    * - Code 
      - Full name 
      - Specification
    * - ``SPED``
      - Speed
      - Measurement
    * - ``ST``
      - Steaming
      - Vessel State
    * - ``LO``
      - Loaded
      - Vessel Condition

`Multi-measurements` are supported since **API V4** and are to be specified as a parameter. 

.. Available catalogues and corresponding measures for vessel statistics can be found in `References`_

************************************************
Web Based API Configurator
************************************************

General
================================================

For developers convenience Marine Benchmark has developed a `web based configurator`_ where you can build URL calls and arguments.
This is a graphical user interface to construct and configure generic API calls. The configurator lets you choose category, subcategory, catalogue with multiple data parameters and conditions to construct powerful API calls.

Configurator URL
================================================

The API configurator can be accessed from the following URL. It is used to browse available data and dynamically construct API URLs.
https://graphicalobjectlibrary.marinebenchmark.com/apiconfigurator/



.. _web based configurator: https://graphicalobjectlibrary.marinebenchmark.com/apiconfigurator/


Authentication
================================================

First time visiting the API configurator page you will be asked to enter your credentials in form of an **API key**.

.. image:: _static/images/key.png
  :width: 100%
  :alt: Alternative text


