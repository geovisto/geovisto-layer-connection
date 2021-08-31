# Geovisto Connection Layer Tool
Extension of the [Geovisto core library](https://github.com/geovisto/geovisto) which provides the connection layer.

This repository is a snapshot of Geoviosto ``tools/layers/connection`` derived from the development repository: [geovisto/geovisto-map](https://github.com/geovisto/geovisto-map).

![sample](https://user-images.githubusercontent.com/1479229/131550255-2bb7fec8-ec9e-446b-99db-66495670727c.png)

## Usage

```js
import { GeovistoConnectionLayerTool } from 'geovisto-layer-connection';
import 'geovisto-layer-connection/dist/index.css';

// create instance of map with given props
const map = Geovisto.createMap({
  // ...
  tools?: Geovisto.createMapToolsManager([
    // instances of Geovisto tools (extensions) which will be directly used in the map
    // ...
    GeovistoConnectionLayerTool.createTool({
      id: "geovisto-tool-layer-connection"
      dimensions?: ...; // provide instance of IConnectionLayerToolDimensions to override dimensions
      geoData?: ...; // provide instance of IGeoDataManager to override geographical data manager
    }),
  ])
});

// rendering of the map
map.draw(Geovisto.getMapConfigManagerFactory().default({
  // initial settings of the map can be overriden by the map config - JSON structure providing user settings 
  // ...
  tools?: [
    // config of Geovisto tools (extensions) used in the map
    {
      "type": "geovisto-tool-layer-connection",
      "id": "geovisto-tool-layer-connection",
      "enabled?": true,
      // mapping of data domains to layer dimensions
      {
      "type": "geovisto-tool-layer-connection",
      "id": "geovisto-tool-layer-connection",
      "data": {
        "geoData": "world centroids", // geo data id
        "from": "from", // data domain
        "to": "to" // data domain
        "direction": false, // animate direction of links
      }
    }
    },
  ]
}));
```

## Installation

```
npm install --save geovisto-layer-connection
```

Peer dependencies:
```
npm install --save geovisto leaflet
```

This package serves as an extension of Geovisto core using the API for Geovisto tools (extensions). Follow Geovisto core on [Github](https://github.com/geovisto/geovisto).

## License

[MIT](https://github.com/geovisto/geovisto-layer-connection/blob/master/LICENSE)

