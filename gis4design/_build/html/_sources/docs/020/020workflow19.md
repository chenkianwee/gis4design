# Search for LiDAR information - Assuming the Building Footprint Data has no Height Information

1. Go to https://viewer.nationalmap.gov/basic/. Search for "university of pennsylvania" at the map window. Then at the dataset window click on Elevation Source Data (3DEP) - Lidar IfSAR -> Lidar Point Cloud (LPC). Click on "Find Products".

    <br/><br/>
    ```{image} ../../_static/020workflow19/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. Download the file : USGS Lidar Point Cloud DE DelawareValley-HD 2015 18SVK483422 LAS 2017
 Published Date:  2017-03-28. Click on "Download LAZ".

     <br/><br/>
     ```{image} ../../_static/020workflow19/img2.png
     :width: 100%
     :align: center
     ```
     <br/><br/>

3. Once downloaded, unzip the file.

    <br/><br/>
    ```{image} ../../_static/020workflow19/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

4. Open the file in Cloud Compare.

    <br/><br/>
    ```{image} ../../_static/020workflow19/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

5. Click on the point cloud layer at the DB Tree Window to make it the active layer. Then go to Edit -> Subsample.

    <br/><br/>
    ```{image} ../../_static/020workflow19/img5.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

6. In the Cloud sub sampling window, choose the "Space" method. In the min. space between points to 5. This means that the density of the point clouds will be reduce to a 5m resolution. Click "OK".

    <br/><br/>
    ```{image} ../../_static/020workflow19/img6.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

7. Once done, the density of the point cloud will be reduced.

    <br/><br/>
    ```{image} ../../_static/020workflow19/img7.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

8. Click on the subsampled point cloud layer. Click on the Save icon. In the Save file window choose "E57 cloud (*.e57)" from the drop down list. e57 is a file format that can be imported into Rhino. Press "Save".

    <br/><br/>
    ```{image} ../../_static/020workflow19/img8.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

9. Open Rhino3D and import the file to check if the export is successful. As the point cloud is georeferenced, once its loaded, zoom extent to locate where is the point cloud.

    <br/><br/>
    ```{image} ../../_static/020workflow19/img9.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
