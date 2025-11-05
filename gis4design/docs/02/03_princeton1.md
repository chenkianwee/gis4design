# Gather all the map onto a canvas
1. We are particularly interested in the Stadium Garage waiting area. So search for "sweetgum drive princeton" on the OSM place search.
    ```{image} ../../_static/princeton/princeton1.png
    :width: 100%
    :align: center
    ```
2. Draw a location point on the garage footprint as the reference point for our future operation. Go to Layer -> Create Layer -> New GeoPackage Layer. In the window fill in the parameters as shown below. 
    - We will be using the Projected CRS: EPSG:32111. The units is in meters. If you are more used to using feet, use EPSG: 3424. [Click here for more information on CRS](../01/02crs.md)
    ```{image} ../../_static/princeton/princeton2.png
    :width: 50%
    :align: center
    ```
3. Draw the point by selecting the layer. Turn on the "Toggle Edit" icon, and "Add Point Feature". Draw the point on the footprint.
    ```{image} ../../_static/princeton/princeton3.png
    :width: 100%
    :align: center
    ```
4. Define the radius of interest from this point ([](../03/024task24)), 3KM. Adjust the transparency of the layer ([](../03/008task8)). [Save the layer as a .gpkg file](../03/007save.md) and remove the temporary layer.
    ```{image} ../../_static/princeton/princeton4.png
    :width: 100%
    :align: center
    ```
5. Grab data from OSM ([](../03/032osm)). Remember to convert the multiparts layer to single parts. You can merge all the path layers together into one. Then save all the layers converting their Projected CRS to EPSG 32111. 
    ```{image} ../../_static/princeton/princeton7.png
    :width: 100%
    :align: center
    ```
6. Get all the building footprint from the osm data. After you convert the multi-polygon layer to single layer. Do the following filter to filter away all the non-buildings.
    ```
    "building" IS NOT NULL
    ```
    ```{image} ../../_static/princeton/princeton8.png
    :width: 100%
    :align: center
    ```

7. Also get the building footprint from the <a href="https://github.com/microsoft/GlobalMLBuildingFootprints/tree/main" target="_blank">Microsoft Building Footprint Project </a>. Follow the instructions [here to get building footprint of your interest](../03/002open_data.md#microsoft-building-footprint-project). Use the following parameters to extract buildings for Princeton. [Then add the geojson into the canvas](../03/003vec_lay.md). [Save the layer as geopackage as geojson has slow performance](../03/007save.md). The building footprint dataset from Microsoft includes **building height**, which makes building a 3d massing model of the site very handy. 
    ```
    location = 'UnitedStates'
    lat = 40.345680487096764
    lng = -74.65880323282136
    ```

8. Download the New Jersey DEM data ([](../03/002open_data3)). It is a huge dataset make sure you at least have 30gb of storage. 
    - Once imported into QGIS, clip it with the buffer area. You can do this by right clicking on the layer -> export -> Save As ... In the dialog box clip the area with the "buffer_area" layer.
    ```{image} ../../_static/princeton/princeton9.png
    :width: 50%
    :align: center
    ```
9. Get the impervious surface data of mercer and middlesex county (where Princeton University is located). Search for "Mercer County Impervious Surface" and download the .gdb file. [Instructions here.](../03/002open_data3.md#download-impervious-surface-mapping-of-new-jersey)

11. Download the parcel information of New Jersey MOD-IV. [Instructions here.](../03/002open_data3.md#download-the-mod-4-parcel-files)

10. Get the road networks of New Jersey. [Instructions here.](../03/002open_data3.md#download-road-network-of-new-jersey)

12. [Get all the features within an area](../03/016vector.md#select-features-by-location). [You can then clip the layers when necessary.](../03/016vector.md#clip-feature-layer) So you are only dealing with the information you need.

13. Get the 3D Las files (point clouds) of the area using the [map tile interface](../03/002open_data3.md#download-dvrpc-2015-lidar-files).
    - load the point cloud files onto qgis Layer -> Add Layer -> Add Point Cloud Layer. To make sure you got the right tiles, superimpose the data onto the map and see if they overlaps with the area of interest. [Save and reproject the layer to the right CRS](../03/007save.md).

14. You can add more information layer onto the canvas as required for your project. With these layers one can already do many analysis.