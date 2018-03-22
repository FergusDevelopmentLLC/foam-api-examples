# FOAM API Examples

This document provides details on how to make authenticated requests to the FOAM REST API to obtain data to drive various web maps. Get started here:
https://f-o-a-m.github.io/foam.developer/index.html

## Authentication

The FOAM REST API requires a header authorization key/value pair for each request. Follow the this tutorial to obtain the Bearer auth string value: https://f-o-a-m.github.io/foam.developer/tutorials/intro_to_api.html 

## Send a test authenticated API request with Postman

1. Install Postman, a REST API utility: https://www.getpostman.com/
2. Download this swagger.json definition of the FOAM REST API: https://f-o-a-m.github.io/foam.developer/3f1f223f5e0965a733c42bdba28adbf5/swagger.json
3. Import downloaded swagger.json into Postman to gain access to all the FOAM API endpoints
4. Double click the https://api-beta.foam.space/beacon?xmin={{xmin}}&ymin={{ymin}}&xmax={{xmax}}&ymax={{ymax}}&zoom={{zoom}} API method
5. Replace the GET url with actual bounding box coordinates, for example: https://api-beta.foam.space/beacon?xmin=-74.024677&ymin=-73.923054&xmax=40.695998&ymax=40.802245
6. Add an authorization key with the Bearer auth string from the Authorization step above
7. Send test request

![](https://i.imgur.com/w3E0UoA.gif)

http://bboxfinder.com is a useful utility for finding a bounding box that fits your area of interest. 

![](http://storage7.static.itmages.com/i/18/0322/h_1521758421_7705106_7f7e0e7d59.png)

Note, when sending a GET /beacon request to the FOAM API, use the latitude/longitude values of your area of interest's bounding box.
* xmin = smallest longitude value
* xmax = largest longitude value
* ymin = smallest latitude value
* ymax = largest latitude value

## Example Maps

See code examples [here](https://github.com/FergusDevelopmentLLC/foam-api-examples/tree/master/examples).

### Leaflet

Simple Leaflet map at displays FOAM CSC data by calling the API. Uses https://github.com/chrisveness/latlon-geohash for datapoint conversion and https://github.com/axios/axios for calling the API.

![](http://storage3.static.itmages.com/i/18/0322/h_1521738128_2846268_36122b1f75.png)

Live example: http://bl.ocks.org/FergusDevelopmentLLC/3b3fd8491b3df85e40d6e0d4b9911493

### Mapbox.GL

Simple Mapbox.GL map at displays FOAM CSC data by calling the API. Uses https://github.com/chrisveness/latlon-geohash for datapoint conversion and https://github.com/axios/axios for calling the API.

![](http://storage7.static.itmages.com/i/18/0322/h_1521738283_6444740_02c3e5b2d8.png)
Live example: http://bl.ocks.org/FergusDevelopmentLLC/e1cb1d18dac41c46c72d8c19f7ef09c8

### Custom markers

Example of how to use a custom marker in Mapbox.GL. Data is from the FOAM API.

![](http://storage8.static.itmages.com/i/18/0322/h_1521738397_6180381_d2d1d3856e.png)
Live example: http://bl.ocks.org/FergusDevelopmentLLC/5769c878d00d8f67569ae5b52c83caad

### Data popup on hover

Example of how to add a marker popup on hover. Data contained in the popup is from from the FOAM API.

![](http://storage6.static.itmages.com/i/18/0322/h_1521738706_3252718_a826d36491.png)
Live example: http://bl.ocks.org/FergusDevelopmentLLC/020933cd26b2133291029fce53a457fb

### CSC search

Example FOAM API search.

Searches that will find matched csc names: "Denver2", "London", "ParisFoamBeta1", "Marriott hotel", etc.

![](https://i.imgur.com/hqGX8qx.gif)
Live example: http://bl.ocks.org/FergusDevelopmentLLC/70150641ddb8c7eb93cebcc689faaae8