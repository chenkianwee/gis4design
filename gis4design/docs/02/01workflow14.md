# Filtering and Inquiries Attributes of Vector Layers

1. For all vector layers in GIS, each shape has an attribute table. Right click on the land_used_clipped layer. Layer -> Open Attribute Table

    <br/><br/>
    ```{image} ../../_static/020workflow14/img1.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

2. The attribute table will open. Scroll down the table and we can see that in total we have 1399 shapes in this layer.

    <br/><br/>
    ```{image} ../../_static/020workflow14/img2.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

3. Choose a shape in the view window. At the bottom left of the attribute table choose "Show Selected Features". The attribute table will only the attributes carry by that shape.

    <br/><br/>
    ```{image} ../../_static/020workflow14/img3.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

4. Lets take a look at the attributes of this shape. This plot is a "Residential" and it is a "Dormitory". Depending on where you find the data, each shapefile carries different set of attributes.  Next, lets filter the shapes and see all the plots that are residential.

    <br/><br/>
    ```{image} ../../_static/020workflow14/img4.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

5. Right click on the layer. Layer -> Filter ...

    <br/><br/>
    ```{image} ../../_static/020workflow14/img5.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

6. Double click on "C_DIG1DESC" in the Fields window. Click on the "=" at the Operators window. Then click "All" at the Values window. All the options will appear. Double click on the "Residential" value. At the "Provider specific filter expression" window you will see the expression being formed. Click on ok.

    <br/><br/>
    ```{image} ../../_static/020workflow14/img6.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

7. You can see at the view window. You can only see the plots that are residential.  You can vary your expression by repeating Step 1-6 with different Fields, Operators and Values.

    <br/><br/>
    ```{image} ../../_static/020workflow14/img7.png
    :width: 100%
    :align: center
    ```
    <br/><br/>

8. To make an expression to filter away all objects that is equal NULL, you cannot use "!=" you have to use the following expression.
    ```
    "building" IS NOT NULL
    ```