# Search for Digital Elevation Model (DEM) - Topography of the Site

1. Go to <a href="https://viewer.nationalmap.gov/basic/" target="_blank">nationalmap</a>, in the search bar at the map view search for "university of pennsylvania".

    <br/><br/>
    ```{image} ../../_static/020workflow17/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. In the Datasets window, go to Elevation Products (3DEP) -> 1 arc-second DEM -> GeoTIFF. Click on "Search Products"

    a. 1 arc second (approximately 30 meters), 1/3 arc second (approximately 10 meters), and 1/9 arc second (approximately 3 meters) read more about it <a href="https://www.e-education.psu.edu/natureofgeoinfo/book/export/html/1835" target="_blank">here</a>.

    <br/><br/>
    ```{image} ../../_static/020workflow17/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. You can see the results here. Click on Footprint and you can see the extent of the data. Download the data.

    <br/><br/>
    ```{image} ../../_static/020workflow17/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

5. Import the .tif file into QGIS ({doc}`../030/0325task26`).

    <br/><br/>
    ```{image} ../../_static/020workflow17/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

6. Lets reproject the raster image to the right CRS. Follow the steps in the exercise "{doc}`020workflow12`" Step 1-6.

7. Clip the raster image to only show the our extent of interest ({doc}`../030/0318task19`). Use the circle drawn in the exercise "Land Use Map" Step 15 to clip it.

    <br/><br/>
    ```{image} ../../_static/020workflow17/img5.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
