================================================
References
================================================

Welcome to Marine Benchmark API Configurator Reference v1.4 for Marine Benchmark API Standard 4.0!

1. Vessel State and Condition
================================================


.. list-table:: Vessel State 
    :widths: 50 50
    :width: 100%
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
    :width: 100%
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


2. Type size name and ID
================================================

.. csv-table:: Type size name and ID
   :file: _static/tables/typesize-id-commercial.csv
   :class: ref-table 
   :widths: 20 20 20 20 20
   :width: 100%
   :delim: ;
   :header-rows: 1

3. Vessel Particular World Fleet Measures 
================================================

The following combinations of catalogues and measures are available for :green:`vessel particular world fleet subcategory`. Popular subcategories,
catalogues and measures are marked in **Bold**.


.. note::
    
    Some catalogues and measure combinations might be temporary unavailable.


.. csv-table:: Vessel Particular World Fleet Measures 
   :file: _static/tables/measures-vessel-particular.csv
   :class: ref-table 
   :widths: 25 25 35 15
   :width: 100%
   :delim: ;
   :header-rows: 1


4. Vessel Distributions Measures
================================================

The following combinations of subcategories, catalogues and measures are available for :green:`vessel distributions`. Popular subcategories,
catalogues and measures are marked in **Bold**. 

.. note::
    
    Some catalogues and measure combinations might be temporary unavailable.


5. Vessel Operational Statistics Measures
================================================

The following combinations of subcategories, catalogues and measures are available for :green:`vessel operational statistics`. Popular subcategories,
catalogues and measures are marked in **Bold**. Catalogues and measures that are under implementation may be marked in *Italic*. 
A catalogue is a nine character code where the last three defines the periodicity, please refer to :ref:`Language and Time Encoding`. 

Periodicity is below marked with (---). 

.. note::
    
    Some catalogues and measure combinations might be temporary unavailable.

