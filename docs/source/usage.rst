Usage
=====

Instalation
-----------
To use InmetPy, install it with pip:

.. code-block:: bash

   pip install inmetpy


Package Overview
================

The inmetpy package is a library which provides a python interface to request data from the Official INMET API. This API provides
access to information and data from all INMET meteorological stations installed in Brazil. The INMET owns more than 700 stations, which
the first one dates from 1925!

You can know more about INMET in the official site (https://portal.inmet.gov.br/) and more about the meteorological stations 
in this nice interface, also official from INMET, https://mapas.inmet.gov.br/.

The link to the API manual is https://portal.inmet.gov.br/manual/manual-de-uso-da-api-esta%C3%A7%C3%B5es



List stations
-------------

.. .. exec_code::
..    :linenos:

..    from inmetpy.inmet_stations import InmetStation 

..    inmet = InmetStation()

..    print(inmet.stations.head(10).to_markdown())


.. The ´inmet´ object contains a list of all stations available at
.. the INMET API, since the first convetional stations to the modern ones.

.. It has two types of stations, "Automatic" stations ("A") and "Traditional" stations ("M", from "Manual").

.. To get filter out just the automatic stations:

.. .. exec_code::
..    :linenos:

..    from inmetpy.inmet_stations import InmetStation 

..    inmet = InmetStation()

..    automatic_stations = inmet.get_auto_stations()

..    print(automatic_stations.head(10).to_markdown())
..    print(len(automatic_stations))


.. Search Stations
.. ---------------

.. It is possible to search stations following either two criterias,
.. the state (or states) that wanted to search or search the closest
.. n stations near by a given location.

.. .. exec_code::
..    :linenos:
..    :caption: Search stations by state

..    from inmetpy.inmet_stations import InmetStation 

..    inmet = InmetStation()

..    # Looking for stations in the Amazonas and Rio de Janeiro states.
..    states = ["AM","RJ"]

..    stations = inmet.search_station_by_state(states)

..    print(stations.head(5).to_markdown())


.. .. exec_code::
..    :linenos:
..    :caption: Search stations by coordinates

..    from inmetpy.inmet_stations import InmetStation 

..    inmet = InmetStation()

..    # Looking for stations in the Amazonas and Rio de Janeiro states.
..    states = ["AM","RJ"]

..    stations = inmet.search_station_by_coords(lat=-22.4212, lon=-42.4518, n_stations = 2)

..    print(stations.head(5).to_markdown())


.. Data from stations
.. ------------------