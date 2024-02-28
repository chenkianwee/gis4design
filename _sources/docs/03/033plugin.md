# Developing QGIS Plugin
- QGIS Python API: https://api.qgis.org/api/annotated.html
- QGIS python tutorials: https://www.qgistutorials.com/en/docs/3/getting_started_with_pyqgis.html
- plugin resources
    - QGIS documentation: https://docs.qgis.org/testing/en/docs/pyqgis_developer_cookbook/plugins/index.html
    - Minimal plugin example: https://github.com/wonder-sk/qgis-minimal-plugin
    - QGIS plugin-CI: 
        - https://opengisch.github.io/qgis-plugin-ci/
        - https://github.com/opengisch/qgis-plugin-ci/
- plugin tutorials
    - building a QGIS plugin: https://www.qgistutorials.com/en/docs/3/building_a_python_plugin.html
    - building a QGIS processing plugin: https://www.qgistutorials.com/en/docs/3/processing_python_plugin.html
    - building plugin: https://training.gismentors.eu/qgis-plugins/build_plugin.html
- plugin examples
    - gis3d: https://github.com/chenkianwee/gis3d
    - shortest path processing algorithm: https://github.com/root676/QNEAT3/blob/master/algs/ShortestPathBetweenPoints.py
    - cityjson loader: https://github.com/cityjson/cityjson-qgis-plugin
    - 3dcitybuilder: https://github.com/arthurRuf/3dcitybuilder
    - third party python library: 
        - https://stackoverflow.com/questions/64043071/using-third-party-python-modules-in-qgis
        - https://pupuweb.com/how-install-python-packages-qgis-python-plugins/
    - Multiple layer parameters
        - https://gis.stackexchange.com/questions/408823/setting-input-to-take-multiple-layers-in-qgis-python-processing-script
    - Get filepath of parameter layer
        - tree_info = self.parameterDefinition(self.TREE_HEIGHT).valueAsJsonObject(parameters[self.TREE_HEIGHT], context)
    -quickapi example
        - https://github.com/gis-ops/tutorials/blob/master/qgis/examples/quick_api/quick_api.py

## Quickstart to develop a processing plugin
1. Create a plugin template with the QGIS plugin "Plugin Builder". We will create a processing plugin, where I am just going to use the default GUI given by QGIS to develop the plugin. The plugin will appear in Processing -> Toolbox -> gis3d
2. Copy and paste the plugin folders to the qgis plugin folders with the following command.
    ```
    cp -r /where/your/plugin/is /home/your_usr_name/.local/share/QGIS/QGIS3/profiles/default/python/plugins
    ```
3. Open QGIS, the plugin should appear in the processing toolbox window
4. Repeat 1- 3 as you make changes to your plugin. Download the plugin "Plugin Reloader". So that you can just reload the plugin without shutting down QGIS.

## Add logo and decide which menu the plugin reside in
- follow the tutorial here
    - https://www.qgistutorials.com/en/docs/3/processing_python_plugin.html
    
## How to edit the input layer
An example script showing how to edit the input layer.
```
def initAlgorithm(self, config):
    ....
    ....
    ....

    self.addParameter(
        QgsProcessingParameterFeatureSource(
            self.TREE_HEIGHT,
            self.tr('Tree Grid Layer'),
            [QgsProcessing.TypeVectorAnyGeometry]
        )
    )

    ....
    ....
    ....

def processAlgorithm(self, parameters, context, feedback):
    ....
    ....
    ....

    tree = self.parameterAsVectorLayer(parameters, self.TREE_HEIGHT, context)
    tree_data = tree.dataProvider()
    tree_data.addAttributes([QgsField(tree_height_name, QVariant.Double)])
    tree.updateFields()

    tree_features = tree.getFeatures()
    tree_fields = tree.fields().names()
    tree_height_field_id = tree_fields.index(tree_height_name)

    total = 100.0 / tree.featureCount() if tree.featureCount() else 0

    for cnt, feature in enumerate(tree_features):
        # Stop the algorithm if cancel button has been clicked
        if feedback.isCanceled():
            break
        
        # Update the progress bar
        feedback.setProgress(int(cnt * total))
        
        fid = feature.id()
        attrs = {tree_height_field_id: 15.2}
        tree_data.changeAttributeValues({fid:attrs})
        
    ....
    ....
    ....
```
## How to create a new layer and populate it with new features and attributes
An example script showing how to create a new sink layer.
```
def initAlgorithm(self, config):
    ....
    ....
    ....

    self.addParameter(QgsProcessingParameterFeatureSource(self.TREE_HEIGHT,
                                                        self.tr('Tree Grid Layer'),
                                                        [QgsProcessing.TypeVectorAnyGeometry])

    self.addParameter(QgsProcessingParameterFeatureSink(self.OUTPUT,
                                                        self.tr('Tree Height Layer'),
                                                        QgsProcessing.TypeVectorPolygon))
    
    ....
    ....
    ....

def processAlgorithm(self, parameters, context, feedback):
    ....
    ....
    ....

    tree = self.parameterAsSource(parameters, self.TREE_HEIGHT, context) #QgsProcessingFeatureSource
    fields = tree.fields()
    fields.append(QgsField(tree_height_name, QVariant.Double))
    tree_features = tree.getFeatures()
    total = 100.0 / tree.featureCount() if tree.featureCount() else 0

    (sink, dest_id) = self.parameterAsSink(parameters, self.OUTPUT, context, fields, tree.wkbType(), tree.sourceCrs())
    for cnt,feature in enumerate(tree_features):
        # Stop the algorithm if cancel button has been clicked
        if feedback.isCanceled():
            break
        
        # Update the progress bar
        feedback.setProgress(int(cnt * total))

        feature.setFields(fields)
        feature[tree_height_name] = 15.3
        sink.addFeature(feature, QgsFeatureSink.FastInsert)

    ....
    ....
    ....
```
## Submitting your plugin to QGIS plugin repository
- official guide: https://docs.qgis.org/testing/en/docs/pyqgis_developer_cookbook/plugins/releasing.html#plugin-structure
    - zip your file and make sure you feel in all the mandatory fields in the metadata.txt
    - get a osgeoid and submit your plugin to https://plugins.qgis.org/plugins/ and wait for approval

- create local respository: https://training.gismentors.eu/qgis-plugins/publish_plugin.html
    - alternatively you can consider setting up a local repository

## Geopandas and laspy
- read and write files with geopandas: https://geopandas.org/en/stable/docs/user_guide/io.html#reading-and-writing-files
- laspy specification: https://www.asprs.org/wp-content/uploads/2019/03/LAS_1_4_r14.pdf