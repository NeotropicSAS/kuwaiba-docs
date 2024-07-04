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

### New Connection

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

1. Set connection name [^note1].
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

### Connectivity Manager Window

Once the initial state of the network that will be used is known, we begin with the creation of the physical circuit Figure 16.

| ![Connectivity Manager window][figure-16] |
|:--:|
| ***Figure 16.** Connectivity Manager window* |

1. Button to select the source port Figure 17.
2. Button to select the source port Figure 18.
3. Type of action to execute between ports Figure 19 and Figure 20.

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

* Figure 19 shows the actions that will be taken between the ports.

| ![Connectivity manager actions][figure-19] |
|:--:|
| ***Figure 19.** Connectivity manager actions* |

#### Actions

##### New Cable/Fiber

[figure-19]: images/figure-connectivity-manager-actions.png

* Figure 20 shows the action that will be taken between the ports.

| ![New fiber window][figure-20] |
|:--:|
| ***Figure 20.** New fiber window* |

[figure-20]: images/figure-new-fiber.png

1. Automatically generated name[^note1].
2. Select link type.
3. Click the button.

Figure 21 shows the first connection.

| ![First connection][figure-21] |
|:--:|
| ***Figure 21.** First connection* |

[figure-21]: images/figure-fist-connection.png

##### New Mirror

Figure 22 shows the steps to execute the action of a new mirror between two ports of a ODF.

| ![New mirror][figure-22] |
|:--:|
| ***Figure 22.** New mirror* |

[figure-22]: images/figure-new-mirror.png

1. Select target port.
2. Select `New Mirror` action.
3. Choose mirror type.
4. Click the button.

##### Select Existing Cable/Fiber

| ![Select existing cable action][figure-23] |
|:--:|
| ***Figure 23.** Select existing cable action* |

[figure-23]: images/figure-select-existing-cable-action.png

1. Select target port.
2. Select Existing Cable/Fiber action.

Figure 24 shows the action to use an existing cable, the cable that was created in the [New Connection][new-connection] section will be used.

[new-connection]: #new-connection

| ![Select existing cable window][figure-24] |
|:--:|
| ***Figure 24.** Select existing cable window* |

[figure-24]: images/figure-select-existing-cable.png

1. Select the cable.
2. Select the tube.
3. Select fiber.
4. Click the button.

##### Select a Cable/Fiber in a Container Template

Before creating a cable using templates, some mirrors and links were created Figure 25.

| ![Select a Cable/Fiber in a Container Template][figure-25] |
|:--:|
| ***Figure 25.** Select a Cable/Fiber in a Container Template action* |

[figure-25]: images/figure-select-cable-template-action.png

1. New mirrors and links added. See [New Mirror][new-mirror] and [New Cable/Fiber][new-cablefiber] actions.
2. Select target port.
3. Select a Cable/Fiber in a Container Template action.

[new-mirror]: #new-mirror
[new-cablefiber]: #new-cablefiber

Figure 26 shows the creation of a cable between building 001 and data center 002 using templates. See [Template Manager][templateman]

| ![Select a Cable/Fiber in a Container Template window][figure-26] |
|:--:|
| ***Figure 26.** Select a Cable/Fiber in a Container Template window* |

[figure-26]: images/figure-select-fiber-in-template.png

1. Select endpoint A of the cable.
2. Select endpoint B of the cable.
3. Select the class.
4. Set the cable name[^note1].
5. Select cable template.
6. Select a tube.
7. Select a fiber.
8. Click the button.

#### Physical Circuit

Figure 27 shows the physical circuit from one port of a MPLSRouter in data center 001 to the other port in a MPLSRouter in data center 002.

| ![Physical circuit][figure-27] |
|:--:|
| ***Figure 27.** Physical circuit* |

[figure-27]: images/figure-physical-circuit.png

Once the physical circuit has been created, you can see the physical path of the MPLSRouter port in the data center 001 Figure 28.

| ![Physical circuit][figure-28] |
|:--:|
| ***Figure 28.** Physical circuit* |

[figure-28]: images/figure-physical-path.png

> **Note** The numbering in Figures 27 and 28 is used to show different perspectives of the same physical circuit. For example (1) is the fiber connected from a MPLSRouter port to an ODF port.

## Creating a Logical Circuit

A logical circuit is a point-to-point connection and is used to represent last mile OSP circuits.

> **Note** To create other types of logic circuits see the [New Logic Circuit][new-logical-circuit] module.

[new-logical-circuit]: ../../logical/new-logical-circuit/index.html

### New Service

Before creating the logical circuit, the service to which it will be associated will be created. Figure 29 shows the step by step to create a service using the [Service Manager][serviceman] module.

[serviceman]: ../../serviceman/index.html

| ![New Service][figure-29] |
|:--:|
| ***Figure 29.** New Service* |

[figure-29]: images/figure-new-service.png

1. Select the customer pool.
2. Select the customer.
3. Select the service pool.
4. Click on the `New Service` button.
5. Choose the type of service.
6. Set the service name[^note1].
7. Click on the `OK` button.

### Create Logical Connection

Figure 30 shows the step by step to create a logical connection.

| ![Create Logical Connection][figure-30] |
|:--:|
| ***Figure 30.** Create Logical Connection* |

[figure-30]: images/figure-logical-circuit.png

1. Select source port.
2. Select target port.
3. Automatically generated name[^note1].
4. Select logical connection class.
5. Search service by name or class.
6. Click on the `Create Logical Connection` button.

Using the [Navigation][navman] module you can search for the new logical connection the Figure 31 shows the [relationships explorer][relationships] for the created logical connection.

[relationships]: ../../navman/index.html#relationships

| ![Logical connection relationships][figure-31] |
|:--:|
| ***Figure 31.** Logical connection relationships* |

[figure-31]: images/figure-logical-connection-relationships.png

[^note1]: Object names in Kuwaiba should use a naming convention to facilitate their management.
