# Search for LiDAR information - Assuming the Building Footprint Data has no Height Information

1. Go to <a href="https://viewer.nationalmap.gov/basic/" target="_blank">nationalmap</a>. Search for "university of pennsylvania" at the map window. Then at the dataset window click on Elevation Source Data (3DEP) - Lidar IfSAR -> Lidar Point Cloud (LPC). Click on "Find Products".

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

3. When you click on the link you will be directed to a ftp site. As chrome is no longer able to open ftp site downloads. We will have to access the ftp folder through our windows file explorer. Copy and paste this path onto your windows explorer address bar.
    ```
    ftp://rockyftp.cr.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/USGS_LPC_DE_DelawareValley_HD_2015_LAS_2017/laz/
    ```
    ```{image} ../../_static/020workflow19/img3a.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

    **a.** In the explorer window search for this file '18SVK483422'

    <br/><br/>
    ```{image} ../../_static/020workflow19/img3b.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

    **b.** Copy and paste the file into your local directory.
    <br/><br/>

    **c.** If you are unable to get the FTP to work. You can download the file for this workflow with this <a href="https://drive.google.com/file/d/1q6N8GHRpKfkh0C-b8StVtc8x2OvZDuL-/view?usp=sharing" target="_blank">link</a>.
    <br/><br/>

4. Open the file in Cloud Compare.

    <br/><br/>
    ```{image} ../../_static/020workflow19/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

    **a.** When ask to shift the coordinates, click No.
    ```{image} ../../_static/020workflow19/img4a.png
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
