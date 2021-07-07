************************************************
Generic API
************************************************

Structure
================================================

API Catalogue Structure
------------------------------------------------

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
------------------------------------------------

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


Web Based API Configurator
================================================

General
------------------------------------------------

For developers convenience Marine Benchmark has developed a `web based configurator`_ where you can build URL calls and arguments.
This is a graphical user interface to construct and configure generic API calls. The configurator lets you choose category, subcategory, catalogue with multiple data parameters and conditions to construct powerful API calls.

Configurator URL
------------------------------------------------

The API configurator can be accessed from the following URL. It is used to browse available data and dynamically construct API URLs.
https://graphicalobjectlibrary.marinebenchmark.com/apiconfigurator/



.. _web based configurator: https://graphicalobjectlibrary.marinebenchmark.com/apiconfigurator/


Authentication
------------------------------------------------

First time visiting the API configurator page you will be asked to enter your credentials in form of an **API key**.

.. image:: _static/images/key.png
  :width: 100%
  :alt: Alternative text


These options can be changed anytime by selecting the **Settings** button in the topright corner.

Constructing API Call
------------------------------------------------

Next, you will be redirected to the API Configurator page which contains three sections.

1.  **Catalogue and measure selection** 
        Here you are required to select category, subcategory, catalogue and
        measures in the listed order. Brief description of each selection can be seen under the drop-down menu. These
        fields are searchable.

2.  **Data selection**
        Here you are required to specify the data selection, typically **Entity1ID**. Optional parameters also include *aggregate by*, 
        *aggregation type*, *top number of records* and *sort order*, which can be enabled/disabled depending on the selection in (1)
        *Catalogue and Measure selection*. You can also select the period by sliding the timeline. A valid Entity1ID
        depends on the selected data category and subcategory, and can consist of a single IMO number, list of IMO
        numbers, type size ID and more.

3.  **Result configuration** 
        Here you can change the response value label, period correction and delivery format and method. The
        constructed API URL call is generated at the bottom and the result can be executed directly or previewed. The
        preview button enables you to see the results in multiple formats, such as a plain JSON, table or even as a graph if
        possible.


Example Queries
------------------------------------------------



1.  Single-measure selection (Speed steaming)
################################################

Say we are simply interested in the daily speed of a vessel, in this case OLJAREN (9236315). We begin by selecting the appropriate category and subcategory.

**Category**: ``Vessel statistics``

**Subcategory**: ``Vessel operational statistics``

We are interested in the daily statistics catalogue.

**Catalogue**: ``Vessel Global Daily``

We only want the vessel speed in steaming condition (+6 kn). By searching for ‘speed steaming’ in the measure field we
find three matching results. Speed steaming total, speed steaming loaded and speed steaming unloaded. Since we do not
care about the vessel loaded or unloaded condition, we select total.

**Measure**: ``SPEEDSTTO - Speed steaming total``

For data selection we specify that we are interested in the entity ``OLJAREN(9236315)`` by setting the state condition in SQL
format as ``Entity1ID in (9236315)``, and leave the rest of the fields empty, as we are not interested in an aggregated result.
Do not forget to specify the period by sliding the timeline.

2.  Multi-measure selection (|CO2| Emission)
################################################
 




.. |CO2| replace:: CO\ :sub:`2`\