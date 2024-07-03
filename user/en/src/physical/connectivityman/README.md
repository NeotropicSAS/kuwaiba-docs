# Connectivity Manager

The connectivity manager module helps with the creation of physical and logical circuits. The access method is shown in Figure 1.

| ![Connectivity manager module][figure-1] |
|:--:|
| ***Figure 1.** Connectivity manager module* |

[figure-1]: images/figure-connectivity-manager-module.png

Clicking on the module will open a window Figure 2.

| ![Connectivity manager window][figure-2] |
|:--:|
| ***Figure 2.** Connectivity manager window* |

[figure-2]: images/figure-connectivity-manager-window.png

1. Link to create a New Object Figure 3.
2. Link to [Template Manager][templateman] module.
3. Link to [Navigation][navman] module

[templateman]: ../../templateman/index.html
[navman]: ../../navman/index.html

| ![Select new object parent][figure-3] |
|:--:|
| ***Figure 3.** Select new object parent* |

[figure-3]: images/figure-select-new-object-parent.png

Figure 3 shows the window that appears after clicking on the `New Object link`, in which a parent is selected for the new object and then an action is chosen for the creation Figure 4.

| ![New Object window][figure-4] |
|:--:|
| ***Figure 4.** New object window* |

[figure-4]: images/figure-new-object-window.png

Figure 4 shows the basic actions to create an object:

1. [New Object][new-object]
2. [New Object from Template][new-object-from-template]
3. [New Multiple Objects][new-multiple-objects]

[new-object]: ../../navman/index.html#new-object
[new-object-from-template]: ../../navman/index.html#new-object-from-template
[new-multiple-objects]: ../../navman/index.html#new-multiple-objects

## Creating a Physical Circuit

The goal of this section is to create a physical circuit between two routers that are located in two data centers (DC) Figure 5.

| ![Initial object view][figure-5] |
|:--:|
| ***Figure 5.** Initial object view* |

[figure-5]: images/figure-object-view-initial.png

The `Building` objects are within a `City` object and each one has a `Rack` object Figure 6, Figure 7 and Figure 8.

| ![Parents of Rack in Data Center 001][figure-6] |
|:--:|
| ***Figure 6.** Parents of Rack in Data Center 001* |

[figure-6]: images/figure-dc-001-rack-001-parents.png

| ![Parents of Rack in Building 001][figure-7] |
|:--:|
| ***Figure 7.** Parents of Rack in Building 001* |

[figure-7]: images/figure-001-rack-001-parents.png

| ![Parents of Rack in Data Center 002][figure-8] |
|:--:|
| ***Figure 8.** Parents of Rack in Data Center 002* |

[figure-8]: images/figure-dc-002-rack-001-parents.png

Each `Rack` object inside the `Building` object contains the equipment to be connected. Below are simple [rack views][rack-view] of the racks that will be used:

[rack-view]: ../../navman/index.html#rack-view

* The `Rack` object in data center 001 contains an `ODF` object and a `MPLSRouter` object of which one of its ports will be used as the start of the physical circuit Figure 9.

| ![Simple Rack View of Rack in Data Center 001][figure-9] |
|:--:|
| ***Figure 9.** Simple Rack View of Rack in Data Center 001* |

[figure-9]: images/figure-dc-001-rack-001-rack-view.png

* The `Rack` object in building 001 contains two `ODF` objects used simply to reach data center 002 Figure 10.

| ![Simple Rack View of Rack in Building 001][figure-10] |
|:--:|
| ***Figure 10.** Simple Rack View of Rack in Building 001* |

* The `Rack` object in data center 002 contains a `ODF` object and a `MPLSRouter` object of which one of the ports will be used as the end of the physical circuit Figure 11.

[figure-10]: images/figure-001-rack-001-rack-view.png

| ![Simple Rack View of Rack in Data Center 002][figure-11] |
|:--:|
| ***Figure 11.** Simple Rack View of Rack in Data Center 002* |

[figure-11]: images/figure-dc-002-rack-001-rack-view.png

Before creating the physical circuit using the [object view][object-view], a connection will be created between data center 001 and building 001.

[object-view]: ../../navman/index.html#object-view

Figure 12 shows how the creation starts.

| ![New connection window][figure-12] |
|:--:|
| ***Figure 12.** New connection window* |

1. Click on the `Connect` button.
2. Select side A of the connection.
3. Select side B of the connection.
4. Click on the `Next` button.

[figure-12]: images/figure-object-view-new-conection-initial.png

Figure 13 shows the definition of the characteristics of the new connection.

| ![Details of new connection][figure-13] |
|:--:|
| ***Figure 13.** Details of new connection* |

1. Set connection name.
2. A cable will be used to connect the two buildings.
3. Set the connection class.
4. Check to use a cable template. See the [Template Manager][templateman] module.
5. Select a template.
6. Click on the `Next` button.

[figure-13]: images/figure-object-view-new-conection-next.png

Figure 14 shows the selection of the connection endpoints.

| ![New connection endpoints][figure-14] |
|:--:|
| ***Figure 14.** New connection endpoints* |

1. Select the endpoint A of the connection.
2. Select the endpoint B of the connection.
3. Click on the `Finish` button.

[figure-14]: images/figure-object-view-new-conection-finish.png

Figure 15 shows the new connection.

| ![Object view with new connection][figure-15] |
|:--:|
| ***Figure 15.** Object view with new connection* |

[figure-15]: images/figure-object-view-new-conection.png

Once the initial state of the network that will be used is known, we begin with the creation of the physical circuit Figure 16.

| ![Connectivity Manager window][figure-16] |
|:--:|
| ***Figure 16.** Connectivity Manager window* |

1. Button to select the source port Figure 17.
2. Button to select the source port Figure 18.
3. Type of action to execute between ports Figure 19.

[figure-16]: images/figure-connectivity-manager-initial.png

* Figure 17 shows the selection of the port from where the physical circuit starts.

| ![Select source port][figure-17] |
|:--:|
| ***Figure 17.** Select source port* |

[figure-17]: images/figure-select-source-port.png

1. The `MPLSRouter` object is searched using its name.
2. Using filters, all ports within the Router are listed. See [Filters][filters] module.
3. Select one of the ports.
4. Click the button.

[filters]: ../../filters/index.html

* Figure 18 shows the selection of the target port.

| ![Select target port][figure-18] |
|:--:|
| ***Figure 18.** Select target port* |

[figure-18]: images/figure-select-target-port.png

1. The `ODF` object is searched using its name.
2. Select one of the ports.
3. Click the button.

* Figure 19 shows the action that will be taken between the ports.

| ![New fiber window][figure-19] |
|:--:|
| ***Figure 19.** New fiber window* |

[figure-19]: images/figure-new-fiber.png

1. Automatically generated name.
2. Select link type.
3. Click the button.

Figure 20 shows the first connection.

| ![First connection][figure-20] |
|:--:|
| ***Figure 20.** First connection* |

[figure-20]: images/figure-fist-connection.png
