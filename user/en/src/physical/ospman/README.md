# Outside Plant Management

The outside plant module manages the OSP views which are composed of nodes and connections and are used to represent the network.

| ![Outside Plant Module](images/figure-physical-ospman.png) |
|:--:|
| ***Figure 1.** Outside plant module* |

| ![Toolbar](images/figure-toolbar.png) |
|:--:|
| ***Figure 2.** Toolbar* |

| Tool | Description |
| -- | -- |
| ![Button open properties panel](images/btn-open-properties-panel.png) | Open properties panel |
| ![Button open view](images/btn-open-view.png) | Open an existing OSP View |
| ![Button create view](images/btn-create-view.png) | Create an OSP View |
| ![Button delete view](images/btn-delete-view.png) | Delete OSP View |
| ![Button save view](images/btn-save-view.png) | Save OSP View |
| ![Button select](images/btn-select.png) | Select a node or connection |
| ![Button add node](images/btn-add-node.png) | Add node |
| ![Button add connections ](images/btn-add-connections.png) | Add connections between two nodes using the existing containers |
| ![Button connect](images/btn-connect.png) | Connect two nodes using a container |
| ![Button run container](images/btn-run-container.png) | Run a container through a single or multiple containers |
| ![Button run link](images/btn-run-link.png) | Run a link through a single or multiple containers |
| ![Button search](images/btn-search.png) | Searches for a node or connection within the view |
| ![Button filter](images/btn-filter.png) | Filter the nodes by class |
| ![Button measure distance](images/btn-measuer-distance.png) | Measure distance |

## Customize the Map

Some characteristics of the map can be changed using the [configuration variables](../../settings/configuration/variables/index.html) below are the changes enabled for the user.

### Map Provider

By default the map is displayed using [OpenLayers](https://openlayers.org/) and the Open Street Map (OSM) tiled layer, to use a different map provider you must update the value of the configuration variable `general.maps.provider` to one of the following allowed values:

* com.neotropic.kuwaiba.modules.commercial.ospman.providers.ol.osm.OsmProvider
* com.neotropic.kuwaiba.modules.commercial.ospman.providers.ol.bmaps.BmapsProvider
* com.neotropic.kuwaiba.modules.commercial.ospman.providers.google.GoogleMapsMapProvider

> **Note:** The *BmapsProvider* and *GoogleMapsMapProvider* require the value of the configuration variable `general.maps.apiKey` to be set.

In addition to the listed providers, it is possible to extend the functionality of this module to use other providers such as [Leaflet](https://leafletjs.com/).

### Map Center and Zoom

When you enter the module, the map has a center and zoom by default, this behavior can be changed by updating the configuration variables:

* `widgets.simplemap.centerLatitude` The default center latitude.
* `widgets.simplemap.centerLongitude` The default center longitude.
* `widgets.simplemap.zoom` The default map zoom.

### Map Labels

To change the color or fill color of the labels of the nodes or edges, the following configuration variables are used:

* `module.ospman.colorForLabels` The color for the map labels.
* `module.ospman.fillColorForEdgeLabels` The fill color for the map edge labels.
* `module.ospman.fillColorForNodeLabels` The fill color for the map node labels.
* `module.ospman.fillColorForSelectedEdgeLabels` The fill color for the map selected edge labels.
* `module.ospman.fillColorForSelectedNodeLabels` The fill color for the map selected node labels.
* `module.ospman.fontSizeForLabels` The font size for the map labels.
* `module.ospman.minZoomForLabels` The minimum zoom level for the map when displaying.

### Default Values of Configuration Variables

The default values ​​of the configuration variables used by this module are listed below by pool:

* General

  * `general.maps.provider` *com.neotropic.kuwaiba.modules.commercial.ospman.providers.ol.osm.OsmProvider*
  * `general.maps.apiKey` *API-KEY*
  * `general.maps.language` *english*

* Widgets
  * `widgets.simplemap.centerLatitude` *30.5632664*
  * `widgets.simplemap.centerLongitude` *-46.6540234*
  * `widgets.simplemap.zoom` *4*

* Outside Plant
  * `module.ospman.colorForLabels` *white*
  * `module.ospman.fillColorForEdgeLabels` *orange*
  * `module.ospman.fillColorForNodeLabels` *blue*
  * `module.ospman.fillColorForSelectedEdgeLabels` *pink*
  * `module.ospman.fillColorForSelectedNodeLabels` *orange*
  * `module.ospman.fontSizeForLabels` *12px*
  * `module.ospman.minZoomForLabels` *12*
