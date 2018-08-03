SQLAlchemy model backend integration examples.

To run this example:

1. Clone the repository::

    git clone https://github.com/flask-admin/flask-admin.git
    cd flask-admin

2. Create and activate a virtual environment::

    virtualenv env
    source env/bin/activate

3. Install requirements::

    pip install -r 'examples/geo_alchemy/requirements.txt'

4. Setup the database::

    psql postgres

    CREATE DATABASE flask_admin_geo;
    CREATE ROLE flask_admin_geo LOGIN PASSWORD 'flask_admin_geo';
    GRANT ALL PRIVILEGES ON DATABASE flask_admin_geo TO flask_admin_geo;
    \q

    psql flask_admin_geo

    CREATE EXTENSION postgis;
    \q

5. Run the application::

    python examples/sqla/app.py

6. You will notice that the maps are not rendered. To see them, you will have
to register for a free account at `Mapbox <https://www.mapbox.com/>`_ and set
the *MAPBOX_MAP_ID* and *MAPBOX_ACCESS_TOKEN* config variables accordingly.

If you'd rather use `Esri Leaflet <https://github.com/Esri/esri-leaflet>`_
then set the *ESRI_BASEMAPS* config variables to a list of the Esri basemaps
you want to use. If there are multiple basemaps in the list, then a layer
control will be added to the map so you can switch between them.
