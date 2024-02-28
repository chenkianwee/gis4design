# Extrude Building Footprint Based on DEM and LiDAR Point Cloud

1. Import the DEM as XYZ file. Then type in the command "PointCloud" to turn the DEM points into point clouds. The processing will be faster ({doc}`01workflow110`).

    <br/><br/>
    ```{image} ../../_static/020workflow112/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. Import the LiDAR point cloud ({doc}`01workflow19`).

    <br/><br/>
    ```{image} ../../_static/020workflow112/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. Install the PointCloudComponent (PCC) plugin from here <a href="https://drive.google.com/drive/folders/1r6z52PILqTQTsyEb95favcRp6x2YzUW9?usp=sharing" target="_blank">here</a>. Open Grasshopper and open the <a href="https://drive.google.com/file/d/1FnlEbFXFCLLovHlDWzI0emzLhtpIBc33/view?usp=sharing" target="_blank">"extrude.gh"</a>. Specify the three inputs for the definition to work.

    <br/><br/>
    ```{image} ../../_static/020workflow112/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

4. Right click on the first ID node. Then choose the LiDAR point cloud in Rhino window. Do it with the second ID node but with the DEM point cloud. Lastly, specify the building footprint shapefile ({doc}`01workflow111`).

    <br/><br/>
    ```{image} ../../_static/020workflow112/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

5. Turn the toggle to True. The building will be extruded.

    <br/><br/>
    ```{image} ../../_static/020workflow112/img5.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

6. You can import all the other data (both Vector and Raster) into Rhino and use it for your design.

    <br/><br/>
    ```{image} ../../_static/020workflow112/img6.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
