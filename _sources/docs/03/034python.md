# Python in QGIS

## Check which Python interpretor QGIS is using 
1. You can check the Python used in QGIS by going to Plugins -> Python Console. In the console type in the following command
    ```
    import sys 
    sys.executable
    ```

## Installing third-party python library in Ubuntu
1. In ubuntu linux, QGIS uses the default system Python. So if you type in the [above command](#check-which-python-interpretor-qgis-is-using) you will get the following result. 
    ```
    usr/bin/python3
    ```

2. If QGIS is using the system default Python. Open up a terminal and you can pip install the necessary libaries here.
    ```
    pip install numpy
    ```

## Installing third-party python library for the gis3d plugin
### Installing in Ubuntu
1. refer to installing third party library in [ubuntu](#installing-third-party-python-library-in-ubuntu). Install the following library for the gis3d plugin.
    ```
    pip install geomie3d==0.0.9
    pip install geopandas==1.0.1
    pip install pyogrio==0.9.0
    pip install laspy==2.5.4
    pip install lazrs==0.6.1
    pip install shapely==2.0.6
    ```
### Installing in Windows
---- work in progress -----