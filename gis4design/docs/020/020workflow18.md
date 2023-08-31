# Search for Building Footprint

1. Search for building footprint at <a href="https://www.opendataphilly.org/" target="_blank">OpenDataPhilly</a>. Search for "building footprint". This is very similar to Task-2b ({doc}`../030/031task22`). Download the shapefile. Unzip the file.

    <br/><br/>
    ```{image} ../../_static/020workflow18/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. Import the shapefile into QGIS ({doc}`../030/032task3`). Reproject the Shapefile into the right CRS ({doc}`../030/0327task28`). Choose the Footprint of interest ("{doc}`020workflow13`, Steps 1-5).

    <br/><br/>
    ```{image} ../../_static/020workflow18/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. If we open the attribute table, we can see that we have the "BASE_ELEVA", "APPROX_HGT" AND "MAX HGT". With this three attributes this is enought to extrude the building footprint and create a 3D model of the area. However, most of the time you will not get such good quality data.

    <br/><br/>
    ```{image} ../../_static/020workflow18/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
