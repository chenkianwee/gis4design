# Vector Tools

## Clip Feature Layer

1. Go to Vector -> Geoprocessing Tools -> Clip ...
    ```{image} ../../_static/0315task16/img1.png
    :width: 100%
    :align: center
    ```

2. Specify the layer to be clipped in the "Input layer parameter", and the clipping layer in the "Clip Layer" parameter. The two layers need to be using the same PCS (refer to task-4 to better understand GCS & PCS).
    ```{image} ../../_static/0315task16/img2.png
    :width: 100%
    :align: center
    ```

3. The clipped layer.
    ```{image} ../../_static/0315task16/img3.png
    :width: 100%
    :align: center
    ```

## Merge Vector Layers
1. Go to Vector -> Data Management Tools -> Merge Vector Layers
2. At the window dialog choose the layers to merge, and the resultant CRS to use. You can decide whether it will be a temporary layer or a permanent layer by specifying it in the dialogue.

## Select Features by Distance
1. Go to Vector -> Research Tools -> Select Within Distance ..
2. In the dialog box fill in the necessary layers. You can specify the distance. In this example we are using a point as the reference layer, and we are selecting from a polygon layer that are the building footprints.
    ```{image} ../../_static/0315task16/img4.png
    :width: 100%
    :align: center
    ```
3. The features will be selected. You can then export the selected features as another layer.

## Select Features by Location
1. Go to Vector -> Research Tools -> Select by Location ..
2. In the dialog box fill in the necessary layers. You can specify the conditions. In this example we are using a polygon as the reference layer, and we are selecting from a polygon layer that are the building footprints.
    ```{image} ../../_static/0315task16/img5.png
    :width: 100%
    :align: center
    ```
3. The features will be selected. You can then export the selected features as another layer.

## Create a grid layer
1. Go to Vector -> Research Tools -> Create Grid ...
2. Fill in the parameters accordingly as shown.
    ```{image} ../../_static/0315task16/img6.png
    :width: 100%
    :align: center
    ```