# Projecting the Maps: From Lat/Lon to Metres

In order to perform spatial analysis (intersection & unions) on the maps, we need to project it from Lat/Lon into metres. Refer to {doc}`../010/011crs` for explanation of Coordinate Reference System (CRS) and projections.

1. Reproject both the site and Land_Use layer ({doc}`../030/0327task28`). The Land_Use layer will take longer as the layer has much more information.

    <br/><br/>
    ```{image} ../../_static/020workflow12/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. Delete the rest of the unprojected layer so that we do not get confused by so many layers. Right click on the layer, Layer -> Remove Layer ...

    <br/><br/>
    ```{image} ../../_static/020workflow12/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. Lastly, since all our layers are using the same projections. Let's set the project CRS to that layer. Right click on the layer. Layer -> Set CRS -> Set Project CRS from Layer.

    <br/><br/>
    ```{image} ../../_static/020workflow12/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

4. We can see that at the bottom right. The CRS has been changed to the layer CRS.

    <br/><br/>
    ```{image} ../../_static/020workflow12/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
