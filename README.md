# Open Source - Stadia Maps with MapLibre Autocomplete

## What is Stadia Maps ?
Stadia Maps provides geolocation data for companies. It provides raster and vector map tiles and lets to integrate them into the website using Leaflet, OpenLayers, or Mapbox GL JS. Its tools enables the creation of maps with support for dozens of languages and scripts. Its offerings include hosted map tiles, offline map tails, static map, navigation, and geospatial APIs.

## What is Stadia Maps Geocoding and autocomplete ?
The Stadia Maps geocoding and autocomplete search APIs help you convert between places and geographic coordinates. Places include points of interest (ex: Times Square), businesses, street addresses, postal codes, and more (see our list of layers). We provide a number of APIs that help you convert between places and coordinates (latitude and longitude) in both directions.

## Web View Example

https://github.com/kecci/opensource-maps-stadia/assets/25241073/7078bc26-73e0-4acd-b88b-5ec067c54600

## Code Example
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic MapLibre Search</title>
    <script src="https://unpkg.com/maplibre-gl@3.2.1/dist/maplibre-gl.js"></script>
    <link href="https://unpkg.com/maplibre-gl@3.2.1/dist/maplibre-gl.css" rel="stylesheet">
    <script src="https://unpkg.com/@stadiamaps/maplibre-search-box/dist/maplibre-search-box.umd.js"></script>
    <link href="https://unpkg.com/@stadiamaps/maplibre-search-box/dist/style.css" rel="stylesheet">
  </head>
  <body style="margin: 0; padding: 0">
    <div id="map" style="height: 100vh; width: 100vw"></div>
    <script type="application/javascript">
      var control = new maplibreSearchBox.MapLibreSearchControl({
        useMapFocusPoint: true,
        onResultSelected: feature => {
          // You can add code here to take some action when a result is selected.
          console.log(feature.geometry.coordinates);
        },
        // You can also use our EU endpoint to keep traffic within the EU using the basePath option:
        // baseUrl: "https://api-eu.stadiamaps.com",
      });
      var map = new maplibregl.Map({
        container: "map",
        // You can also use our EU endpoints here by changing the host to tiles-eu.stadiamaps.com
        style: "https://tiles.stadiamaps.com/styles/alidade_smooth.json", // stylesheet location
        center: [-74.5, 40], // starting position [lng, lat]
        zoom: 2, // starting zoom
      });
      map.addControl(control, "top-left");
    </script>
  </body>
</html>

```
