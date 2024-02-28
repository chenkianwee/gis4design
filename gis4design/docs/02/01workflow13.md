# Land Use Map

In this exercise we will manipulate the Land Use layer to get a Land Use map around our site.

1. Click on the Land Use layer to make sure it is the active layer.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. We will select and export only the land parcels around our site. Choose the "Select Features by Radius".

    <br/><br/>
    ```{image} ../../_static/020workflow13/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. Click on the centre of our plot and enter 1000m radius. Press enter and the features will be selected.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

4. All the features of the layers within that radius will be chosen.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

5. Export the selected features into a separate layer ({doc}`../03/007save`).  Make sure you tick the "Save only selected features" parameter. It will take some time as it is a big file.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img5.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

6. Once processed we can see the layer. Turn off the "Land_Use_projected" layer.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img6.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

7. Click on the "Select Feature(s)" function.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img7.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

8. Choose the roads on the view screen. We can see that the whole road network of Philly is drawn as a single shape. It is very big and we do not need the road network for the Land Use map. Let's delete the road network from the layer.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img8.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

9. Click on Landuse_interest layer to make it the active layer. Click on the "Toggle Editing".

    <br/><br/>
    ```{image} ../../_static/020workflow13/img9.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

10. Select the road network shape and press delete.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img10.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

11. Click on "Toggle Editing" and a prompt will pop up asking you to save the change. Click on the "Save" button.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img11.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

12. We will have all the land use shape around the site.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img12.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

13. Now we can categorise the map ({doc}`../03/017categorize`).

    <br/><br/>
    ```{image} ../../_static/020workflow13/img13.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

14. You can then compose the map with layout manager ({doc}`../03/018task18`) and export it as an image.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img14.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

15. For a more precise map of strictly 800m radius from the site. We can clip the shapes. First, calculate the centroid of our site ({doc}`../03/023task23`). Then using the centroid draw a circle ({doc}`../03/024task24`). Using the circle drawn clip the Land Use layer ({doc}`../03/016vector`). If the Clip operation fails, go to ({doc}`../03/025task25`) and turn off The result of the clip is shown below. Repeat step 13 to 14 to get the Landuse map.

    <br/><br/>
    ```{image} ../../_static/020workflow13/img15.png
    :width: 100%
    :align: center
    ```
    <br/><br/>
