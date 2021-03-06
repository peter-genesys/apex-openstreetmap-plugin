# Oracle APEX OpenStreetMap Plugin
Oracle APEX Plugin for OpenStreetMap maps 

![GitHub Logo](/img/scr.png)

## Assets

### JavaScript

This plugin uses [Leaflet 1.4.0](https://leafletjs.com/) lib for interactive maps. This lib is integrated into the plugin as two files:

```
assets/js/leaflet/leaflet.js
assets/js/leaflet/leaflet.css
```

The main map rendering script [map.js](src/js/map.js) is integrated into the plugin as well.

```
assets/js/map.js
```

### Map markers

To support different color markers the [leaflet-color-markers](https://github.com/pointhi/leaflet-color-markers) were integrated into the plugin:

```
assets/markers/
```

## Plugin attributes

| Name        | Type            | Required | Default Value     |
|-------------|-----------------|----------|-------------------|
| Height      | Text            | Yes      | 700px             |
| Source      | PL/SQL Code     | Yes      | _Described below_ |

The `Source` attribute should contain PL/SQL request or procedure call that returns one string value result with JSON in the next format:

```json
{
  "markers": [
    {
      "point": [50.45, 30.523333],
      "color": "red",
      "text": "Red marker text"
    },
    {
      "point": [50.4, 30.53],
      "color": "blue",
      "text": "Blue marker text"
    },
    {
      "point": [50.41, 30.5],
      "color": "green",
      "text": "Green marker text"
    }
  ],
  "polygons": [
    {
      "color": "blue",
      "text": "Blue polygon text",
      "points": [
        [50.45, 30.523333],
        [50.4, 30.53],
        [50.41, 30.5],
      ]
    },
    {
      "color": "red",
      "text": "Red polygon text",
      "points": [
        [50.55, 30.523333],
        [50.5, 30.53],
        [50.51, 30.5],
      ]
    },
    {
      "color": "green",
      "text": "Green polygon text",
      "points": [
        [50.45, 30.623333],
        [50.4, 30.63],
        [50.41, 30.6],
      ]
    }
  ]
}
```
