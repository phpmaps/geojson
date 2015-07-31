# Metadata Facts

##Japan's Municipalities

![alt text](images/Municipalities.png "Municipalities")

###MunicipalitiesDemographics.geojson
Feature Count: 1901

Min Scale: 1500001

Max Scale: 500001

Spatial Reference:4326

Max Allowable Offset: None

Geometry Precision: None

Source: http://demographics2.arcgis.com/arcgis/rest/services/JPN_Demographics_and_Boundaries/MapServer/8


###MunicipalitiesStandardGeographyQuery.geojson
Feature Count: 1901

FilterGeographyLayerID: "JP.Country"

FilterGeographyWhere: "Japan"

GeneralizationLevel: "6"

Spatial Reference:4326

SubGeographyLayerID: "JP.Municipalities"

Source: http://geoenrich.arcgis.com/arcgis/rest/services/World/GeoenrichmentServer/StandardGeographyQuery/execute?sourceCountry=JP&outSR=%7B%22wkid%22%3A102100%2C%22latestWkid%22%3A3857%7D&returnGeometry=true&generalizationLevel=6&returnSubGeographyLayer=true&geographyLayers=JP.Country&geographyQuery=Japan&subGeographyLayer=JP.Prefectures&f=json




##Japan's Prefectures

![alt text](images/Prefecture.png "Prefecture")

###PrefectureDemographics.geojson
Feature Count: 47

Min Scale: 20000000

Max Scale: 18000001

Spatial Reference:4326

Max Allowable Offset: None

Geometry Precision: None

Source: http://demographics2.arcgis.com/arcgis/rest/services/JPN_Demographics_and_Boundaries/MapServer/6



###PrefectureStandardGeographyQuery.geojson
Feature Count: 47

FilterGeographyLayerID: "JP.Country"

FilterGeographyWhere: "Japan"

GeneralizationLevel: "6"

Spatial Reference:4326

SubGeographyLayerID: "JP.Prefectures"

Source: http://geoenrich.arcgis.com/arcgis/rest/services/World/GeoenrichmentServer/StandardGeographyQuery/execute?sourceCountry=JP&outSR=%7B%22wkid%22%3A102100%2C%22latestWkid%22%3A3857%7D&returnGeometry=true&generalizationLevel=6&returnSubGeographyLayer=true&geographyLayers=JP.Country&geographyQuery=Japan&subGeographyLayer=JP.Prefectures&f=json

##Developer Tips

* Browse global data collection to explore hierarches quickly
* Highest quality web service data (for geometry and property data) contained in Esri demographics services (look for 3 digit country code in Map Service Name)
 * http://demographics1.arcgis.com/arcgis/rest/services
 * http://demographics2.arcgis.com/arcgis/rest/services
 * http://demographics3.arcgis.com/arcgis/rest/services
 * http://demographics4.arcgis.com/arcgis/rest/services
 * http://demographics5.arcgis.com/arcgis/rest/services
* Use Query operation to fetch geometry for desired layers in the map service ``` where=1=1  ``` and ```f=json``` (spatial reference should be 4326)
* Do not query for attributes / properties unless you understand credit model
*  Services often have a limit on the number of features that can be returned, so it's a good idea to make a request to ```returnCountOnly``` and then paginate requests in chunks of 1000
* If rough data (generalized at level 6) is all that is needed it's possible to get geometries using StandardGeographyQuery requests - which can also return centroids
* To convert Esri Geometry to GeoJSON use this project - [http://terraformer.io/](http://terraformer.io/)
* To recreate a map service from a data source use this project - [http://koopjs.github.io/](http://koopjs.github.io/)


