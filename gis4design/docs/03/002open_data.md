# Search for Open Geospatial Data

Depending on the location of your site, you will have to go the respective local authority website to obtain open geospatial data. Sometimes you can [get open data globally from a single source such as OpenStreetMap](032osm.md#install-osm-download) and the [Microsoft building footprint project](#microsoft-building-footprint-project).

## Open 3D dataset around the world
- https://3d.bk.tudelft.nl/opendata/opencities/

## Microsoft Building Footprint Project
1. Go to https://github.com/microsoft/GlobalMLBuildingFootprints to have a better understanding of the dataset.
2. Install the necessary Python library and run the code to get the dataset.
    ```
    pip install pandas geopandas shapely
    ```
3. Run the following python script to grab data from the server.
    ```
    import math
    import pathlib
    import pandas as pd
    import geopandas as gpd
    from shapely.geometry import shape
    #==========================================================================================================================================================
    # region: Parameters
    #==========================================================================================================================================================
    location = 'UnitedStates' # find all the location names in this csv https://minedbuildings.blob.core.windows.net/global-buildings/dataset-links.csv
    lat = 40.345680487096764
    lng = -74.65880323282136
    res_dir = '/result/dir'

    # endregion
    #==========================================================================================================================================================
    # region: Functions
    #==========================================================================================================================================================
    def get_quadkey(lat: float, lng: float, zoom_lvl: int = 9) -> str:
        # https://medium.com/@biz.soing/generating-quadkeys-83aa2b8018b7
        x = int((lng + 180) / 360 * (1 << zoom_lvl))
        y = int((1 - math.log(math.tan(math.radians(lat)) + 1 / math.cos(math.radians(lat))) / math.pi) / 2 * (1 << zoom_lvl))
        quadkey = ''
        for i in range(zoom_lvl, 0, -1):
            digit = 0
            mask = 1 << (i - 1)
            if (x & mask) != 0:
                digit += 1
            if (y & mask) != 0:
                digit += 2
            quadkey += str(digit)
        return quadkey

    def get_footprint(location: str, lat: float, lng: float, res_dir: str, zoom_lvl: int = 9):
        # this is the name of the geography you want to retrieve. update to meet your needs
        target_quadkey = get_quadkey(lat, lng, zoom_lvl=zoom_lvl)
        target_quadkey = int(target_quadkey)
        dataset_links = pd.read_csv("https://minedbuildings.blob.core.windows.net/global-buildings/dataset-links.csv")
        loc_links = dataset_links[dataset_links.Location == location]
        for cnt, row in loc_links.iterrows():
            quadkey = row.QuadKey
            if target_quadkey == quadkey:
                print('found', quadkey)
                df = pd.read_json(row.Url, lines=True)
                df['geometry'] = df['geometry'].apply(shape)
                gdf = gpd.GeoDataFrame(df, crs=4326)
                res_path = pathlib.PurePath(res_dir,str(row.QuadKey) + '.geojson')
                gdf.to_file(str(res_path), driver='GeoJSON')

    # endregion
    #==========================================================================================================================================================
    # region: Main
    #==========================================================================================================================================================
    if __name__ == "__main__":
        get_footprint(location, lat, lng, res_dir)
    # endregion
    ```
4. The script will download a geojson quad by specifying the lat, lng of the space of interest.