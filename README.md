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

## Example

```js
// Add a basic graticule with divisions every 20 degrees
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
```

<a href="http://blog.thematicmapping.org/2013/07/creating-graticule-with-leaflet.html">More information</a>
