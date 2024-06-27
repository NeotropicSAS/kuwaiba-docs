# Configuration Variables

The configuration variables module in Figure 1 belongs to the `Settings` category and manages configuration variables pools and configuration variables.

| ![Configuration Variables Module](images/toolbar-settings-configuration-variables.png) |
|:--:|
| ***Figure 1.** Configuration variables module* |

## Configuration Variable Pool

A configuration variable pool is a group of configuration variables.

The steps to create a pool are as follows:

* Click on the button to manage pools Figure 2.

| ![Manage Pools](images/manage-pools.png) |
|:--:|
| ***Figure 2.** Manage pools button* |

* In the manage pools window click on the new pool button Figure 3.

| ![Manage Pools](images/manage-pools-window.png) |
|:--:|
| ***Figure 3.** Manage pools window* |

* Enter a name and description for the new pool and click the OK button Figure 4.

| ![Manage Pools](images/new-pool-window.png) |
|:--:|
| ***Figure 4.** New pool window* |

* The pool was created and can be edited or deleted from the pool manages window Figure 5.

| ![Manage Pool](images/manage-pool.png) |
|:--:|
| ***Figure 5.** Manage Pools Window* |

## Configuration Variable

A configuration variable is a global variable that can be used in any module or script and the value is accessed via name using the `ApplicationEntityManager API`.

The steps to create a configuration variable are as follows:

* Click on the new configuration variable button Figure 6.

| ![Manage Pool](images/new-configuration-variable.png) |
|:--:|
| ***Figure 6.** New configuration variable button* |

* Set the properties of the configuration variable Figure 7 and click the OK button.

| ![Manage Pool](images/new-configuration-variable-window.png) |
|:--:|
| ***Figure 7.** New configuration variable window* |

To manage the configuration variable, select the configuration variable pool or search by name, select the variable you want to edit or delete and use the property sheet as shown in Figure 8.

| ![Manage Pool](images/edit-new-configuration-variable.png) |
|:--:|
| ***Figure 8.** Edit configuration variable* |

## Default Values

The default values ​​of the configuration variables are listed below by module:

### Outside Plant Management

The default values ​​of the configuration variables used by the [Outside Plant Management][ospman] are listed below by pool:

[ospman]: ../../../physical/ospman/index.html#customize-the-map

* General

  * `general.maps.provider` *com.neotropic.kuwaiba.modules.commercial.ospman.providers.ol.osm.OsmProvider*
  * `general.maps.apiKey` *null*
  * `general.maps.language` *english*
  * `general.maps.provider.bmaps.imagerySet` *Aerial*

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
