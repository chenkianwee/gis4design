# Estimate Tree Heights with Impervious Surface Layer and LAS
1. Create a [grid layer](../03/016vector.md#create-a-grid-layer) with the following parameters. Save it as a permanent layer before performing the next step.
    ```
    Grid type: Rectangle
    Grid extent: "choose the buffer layer"
    Horizontal spacing: 5 meters
    Vertical spacing: 5 meters
    Grid CRS: epsg 32111
    ```

2. Select the grids that did not intersect with the impervious surface layer. 
    - [First select the gird that is intersecting the impervious surface layer](../03/016vector.md#select-features-by-location)
    - Inverse the selection and you will get the result. Edit -> Select -> Invert Feature Selection
    - [Save the invert selection as a new layer](../03/007save.md).

3. Download and install the gis3d plugin. <a href="https://github.com/chenkianwee/gis3d?tab=readme-ov-file#installation" target="_blank">https://github.com/chenkianwee/gis3d?tab=readme-ov-file#installation</a> 

4. Once installed you should be able to find the gis3d plugin under Plugins -> gis3d -> tree_height_grids. Key in the parameters as follows: 
    ```
    Tree Grid Layer: 5m grid that was created in the previous step
    Point Clouds: select all the point clouds that is loaded in the canvas
    Percentile of Point Height to Assume as Tree Height: 90
    Minimum Height to be considered a Tree (meter): 3.0
    Name of Attribute to Store Estimated Tree Heights: gis3d_tree_height
    Use Points in this Classification for Tree Heights Analysis: Unclassified 
    ```
    ```{image} ../../_static/princeton/princeton12.png
    :width: 100%
    :align: center
    ```
    - run the algorithm depending on your computer specification and the size of your data set. The processing time will differ. The result of the processing can be [visualized in falsecolor](../03/017categorize.md) as shown below.
    ```{image} ../../_static/princeton/princeton10.png
    :width: 100%
    :align: center
    ```
5. Once processing is done. The layer will have a new attribute appended to it.
    ```{image} ../../_static/princeton/princeton11.png
    :width: 100%
    :align: center
    ```