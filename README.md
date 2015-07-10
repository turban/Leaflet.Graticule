Leaflet.Graticule
=================

Generate a graticule grid of latitude and longitude lines.

## API

### `L.graticule(options)`

Create a new Graticule layer which inherits from `L.GeoJSON`. Options is an
optional options object with the following properties:

* `interval`: the gap between each graticule line, in degrees
* `style`: [path options](http://leafletjs.com/reference.html#path-options) for
  the generated lines
* `extent`: an optional L.LatLngBounds that specifies the limits of the graticule,
  doesn't work well with non-Web Mercator/WGS84 projections such as Mollweide

## Example

```js
// Add a basic graticule with divisions every 20 degrees for the entire world
// as a layer on a map
L.graticule().addTo(map);

// Specify divisions every 10 degrees
L.graticule({ interval: 10 }).addTo(map);

// Specify bold red lines instead of thin grey lines
L.graticule({
    style: {
        color: '#f00',
        weight: 10
    }
}).addTo(map);

//Create a graticule with divisions every 20 degrees and 
//limit its extent to the current map view
L.graticule({ extent: map.getBounds() }).addTo(map);

//Change the interval of the graticule
var graticule = L.graticule().addTo(map);
graticule.setInterval(1);
graticule.refresh();

//Change the extent of the graticule to the current map view bounds
graticule.setExtent(map.getBounds());
graticule.refresh();

```

<a href="http://blog.thematicmapping.org/2013/07/creating-graticule-with-leaflet.html">More information</a>
