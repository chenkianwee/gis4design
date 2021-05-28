# Search for Surface Temperature Data

1. Register an account at <a href="https://ers.cr.usgs.gov/register/" target="_blank">USGS</a>

    <br/><br/>
    ```{image} ../../_static/020workflow15/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. Once registered, go to <a href="https://earthexplorer.usgs.gov/" target="_blank">Earthexplorer</a>. In the Address/Place parameter key in "university of pennsylvania". The search will return "Philadelphia PA, 19104, USA". Click on the result.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. Once clicked, the area will be automatically translated into Lat/Lon. Then click on the Data Sets button.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

4. In the Data Sets section, go to Landsat -> Landsat Collection 1 -> Landsat C1 Analysis Ready Data (ARD) -> U.S. Landsat 4-8 ARD. Then click on the Results button.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

5. In the result window, you can scroll through the results. Click on the footprint and JPG icon to see the extent of the data on the map view. You can also the date the data is acquired. Next, click on the Download button.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img5.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

6. Login to your USGS account. Download the "Provisional Surface Temperature" Data.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img6.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

7. Next unzip the file.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img7.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

8. In the unzip folder there will be 13 files. To look at the metadata of each file, open the XML file with your browser and scroll through the information to understand what data does each file carries.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img8.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

9. From reading through the metadata, we can tell that the file ending with "ST" is the surface temperature data. The units is in Kelvin and the spatial resolution is 30m by 30m. The maximum temperature range is 3730 and the minimum is 1500. If you look at the metafile it says the data have to be scaled by 0.1. So the maximum is 373K and 150K. You can also read about the information from this <a href="https://www.usgs.gov/land-resources/nli/landsat/landsat-provisional-surface-temperature?qt-science_support_page_related_con=0#qt-science_support_page_related_con" target="_blank">website</a>.

    <br/><br/>
    ```{image} ../../_static/020workflow15/img9.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
