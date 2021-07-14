================================================
References
================================================


General
################################################


Vessel State and Conditions
================================================


.. list-table:: Vessel State 
    :widths: 50 50
    :header-rows: 1
    :class: tight-table, url-table

    * - Condition
      - Description
    * - **Total**
      - Independent of loaded or unloaded condition
    * - **Loaded**
      - Vessel in loaded conditionllo
    * - **Unloaded**
      - Vessel in Unloaded conditionllo


.. list-table:: Vessel Condition
    :widths: 50 50
    :header-rows: 1
    :class: tight-table, url-table

    * - State
      - Description 
    * - **Total**
      - Total. Independent of speed and area
    * - **Steaming**
      - Vessel speed above 6 knots
    * - **Maneuvering**
      - Vessel speed between 1 and 6 knots
    * - **Moving**
      - Vessel speed above 1 knot
    * - **Anchored**
      - Vessel speed below 1 knot in a defined anchor area
    * - **Moored**
      - Vessel speed below 1 knot in a defined and valid port area
    * - **Out of Traffic** 
      - Vessel speed below 1 knot and classified as out of traffic
    * - **Still undefined**
      - Vessel speed below 1 knot and not in a defined area
    * - **Still**
      - Vessel speed below 1 knot


Type size name and ID
================================================

The following shows the *name* and *ID* to available type sizes. These are essential when constructing API calls regarding type sizes, for example as ``Entity1ID in(210103)``.

.. csv-table:: Type size name and ID
   :file: _static/tables/typesize-id-commercial.csv
   :class: ref-table 
   :widths: 20 20 20 20 20
   :delim: ;
   :header-rows: 1


.. note::
    
    Some statistics may be unavailable for certain type sizes. 


Vessel Particular World Fleet Measures 
================================================

The following combinations of catalogues and measures are available for :green:`vessel particular world fleet subcategory`. Popular subcategories,
catalogues and measures are marked in **Bold**.


.. note::
    
    Some catalogue and measure combinations might be temporary unavailable.


.. csv-table:: Particular World Fleet Measures 
   :file: _static/tables/measures-vessel-particular.csv
   :class: ref-table 
   :widths: 25 25 35 15
   :delim: ;
   :header-rows: 1


Distributions Measures
================================================

The following combinations of subcategories, catalogues and measures are available for :green:`vessel distributions`. Popular subcategories,
catalogues and measures are marked in **Bold**. 

.. note::
    
    Some catalogue and measure combinations might be temporary unavailable.


.. csv-table:: Distributions Measures
   :file: _static/tables/measures-distributions.csv
   :class: ref-table 
   :delim: ;
   :header-rows: 1

Operational Statistics Measures
================================================

The following combinations of subcategories, catalogues and measures are available for :green:`vessel operational statistics`. Popular subcategories,
catalogues and measures are marked in **Bold**. Catalogues and measures that are under implementation may be marked in *Italic*. 
A catalogue is a nine character code where the last three defines the periodicity, please refer to :ref:`Language and Time Encoding`. 

Periodicity is below marked with (---).  

.. note::
    
    Some catalogue and measure combinations might be temporary unavailable.

.. csv-table:: Operational Statistics Measures
   :file: _static/tables/measures-operational.csv
   :class: ref-table 
   :delim: ;
   :header-rows: 1