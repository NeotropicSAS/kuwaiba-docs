# SDH Networks

This module allows to create end-to-end virtual circuits and all other logical entities required by the SDH protocol[^1]. Let’s introduce some concepts first. See [Figure 1][figure-1] for sample connection that illustrate the following terms.

1. `TransportLink` A point-to-point logical connection that represents a single **STMX**. By default, the TransportLinks included in Kuwaiba are `SMT1`, `STM4`, `STM16`, `STM64` and `STM256`.
2. `ContainerLink` It’s a logical connection that may or may not have multiple hops and connects ports within the boundaries of the transport network. A `ContainerLink` ends where at least one `TransportLinks` ends, but in its path, the `ContainerLink` may have used many TransportLinks. In simple terms, a `ContainerLink` is an SDH virtual circuit. By default there are 5 types of ContainerLinks defined: `VC12`, `VC3`, `VC4`, `VC4-04` and `VC4-16`. The latter two provide support for concatenation.
3. `TributaryLink` Objects of this type are not circuits themselves, they rather use actual virtual circuits (ContainerLinks) and end in the ports where the SDH service is delivered to the customer (usually tributary ports).

| ![Sample multi-hop SDH circuit][figure-1] |
|:--:|
| ***Figure 1.** Sample multi-hop SDH circuit and its relationships with services, customers and physical resources* |

[figure-1]: images/figure-sdh-module-description.png

In short, Transport and ContainerLinks provide the foundations for the hierarchy, while the TributaryLinks provide information about where the circuits are delivered (that is, what are the endpoints of the connections).

## Creating an SDH view

To create an SDH topology, go to the menu option [Figure 2][figure-2].

| ![SDH Module][figure-2] |
|:--:|
| ***Figure 2.** SDH Module* |

[figure-2]: images/figure-sdh-module.png

This will open an empty canvas similar to the [Topology Designer][topology].

[topology]: ../../planning/topoman/index.html

| ![SDH module toolbar and canvas][figure-3] |
|:--:|
| ***Figure 3.** SDH canvas* |

[figure-3]: images/figure-canvas.png

The table below lists the tools and their description:

| Tool | Description |
| :--: | -- |
| ![Tool 1][tool-1] | Open SDH view |
| ![Tool 2][tool-2] | New SDH view |
| ![Tool 3][tool-3] | Remove view |
| ![Tool 4][tool-4] | Add devices |
| ![Tool 5][tool-5] | Remove from database and view |
| ![Tool 6][tool-6] | Remove from view |
| ![Tool 7][tool-7] | Export as image |
| ![Tool connect][tool-connect] | Connect |

[tool-1]: images/tool-1.png
[tool-2]: images/tool-2.png
[tool-3]: images/tool-3.png
[tool-4]: images/tool-4.png
[tool-5]: images/tool-5.png
[tool-6]: images/tool-6.png
[tool-7]: images/tool-7.png
[tool-connect]: images/tool-connect.png

Using the tool to add devices ![Add devices tool][tool-4] add the equipment you need [Figure 4][figure-4].

| ![Add devices window][figure-4] |
|:--:|
| ***Figure 4.** Add devices window* |

[figure-4]: images/figure-add-devices-window.png

Let’s consider this 4 equipment topology [Figure 5][figure-5].

| ![SDH Topology][figure-5] |
|:--:|
| ***Figure 5.** Some routers and multiplexers in an SDH topology* |

[figure-5]: images/figure-sdh-topology.png

What we are going to do is to create a ring using STM-4 on one branch and SMT-1 on the other. We will create a VC12 between SDH-87 and Router 1. Each equipment has the same board/port layout: Two boards [Figure 6][figure-6], a tributary and an aggregate one, with two ports each [Figure 7][figure-7].

| ![Board layout][figure-6] |
|:--:|
| ***Figure 6.** Board layout* |

[figure-6]: images/figure-board-layout.png

| ![Port layout][figure-7] |
|:--:|
| ***Figure 7.** Port layout* |

[figure-7]: images/figure-port-layout.png

## Creating TransportLinks

First, we have to create the most basic support, that is the TransportLinks (STMX). Use the connect tool ![connect tool][tool-connect] and drag a line from one equipment to the other. That will start a wizard [Figure 8][figure-8].

| ![Select connection type window][figure-8] |
|:--:|
| ***Figure 8.** Select connection type window* |

[figure-8]: images/figure-select-connection-type-smtx.png

The first step of the wizard will request for the basic information: name and type [Figure 9][figure-9]

| ![Creating a TransporLink, step 1][figure-9] |
|:--:|
| ***Figure 9.** Creating a TransporLink, step 1* |

[figure-9]: images/figure-create-smtx-window.png

The second will request the connection endpoints, which will always be aggregate ports.

| ![Creating a TransporLink, step 2][figure-10] |
|:--:|
| ***Figure 10.** Creating a TransporLink, step 2* |

[figure-10]: images/figure-create-smtx-endpoints-window.png

After repeating the procedure three more times, the ring will be finished. In the [Figure 11][figure-11]

| ![SDH ring][figure-11] |
|:--:|
| ***Figure 11.** SDH ring* |

[figure-11]: images/figure-sdh-ring.png

## Creating ContainerLinks

The next level in the hierarchy is the set of structured high-order circuits (VC4) that will contain the E1s that we will add later. We will create three VC4: A long one, from SDH-87 to Router 1, a short one, from SDH-87 to Router 2, and finally another short one between Router 2 and Router 1. This will provide two paths to route the E1s later on. To create the VC4 connections (a.k.a. ContainerLinks). To create the first ContainerLink using the Connection tool ![Connection Tool][tool-connect], let’s drag a line between the SDH-87 and the Router 1. That will start a wizard.

| ![New ContainerLink, step 1][figure-12] |
|:--:|
| ***Figure 12.** New ContainerLink, step 1* |

[figure-12]: images/figure-create-vc4-window.png

Again, the first step is about basic information: Container name and type. We will create a simple VC4. The next step is about routes. You will find two routes. In the center panel, the detail of the chosen route will be displayed.

| ![New ContainerLink, step 2][figure-13] |
|:--:|
| ***Figure 13.** New ContainerLink, step 2* |

[figure-13]: images/figure-create-vc4-routes.png

The next step will ask you to define what timeslots you will use from each TransportLink in the route [Figure 14][figure-14]. To select the timeslot from the list. This list will be populated with the available timeslots, but it will also inform you what timelots are already in use and who’s using them.

| ![New ContainerLink, step 3][figure-14] |
|:--:|
| ***Figure 14.** New ContainerLink, step 3* |

[figure-14]: images/figure-create-vc4-hop.png

It’s not necessary to select any endpoint ports, since they’re taken from the underlying TransportLinks. Once created, you won’t see anything different in the view, since the only connections to be displayed are the TransportLinks.

## Creating TributaryLinks

The last step is to create a TributaryLink, that is, the actual E1 to be delivered. For that, we have to press the connection tool ![Connection Tool][tool-connect]. As usual, drag a line between the end equipment, in this case, SDH-87 and Router 1. This will open another wizard.

| ![New TributaryLink, step 1][figure-15] |
|:--:|
| ***Figure 15.** New TributaryLink, step 1* |

[figure-15]: images/figure-create-tributary-link-window.png

In the next step, you will be requested to pick a route. Note that the STM4-based route won’t be offered, as it doesn’t have ContainerLinks to transport the TributaryLink.

| ![New TributaryLink, step 2][figure-16] |
|:--:|
| ***Figure 16.** New TributaryLink, step 2* |

[figure-16]: images/figure-create-tributary-link-routes.png

The third step consists of choosing the timeslot in the ContainerLink (VC4)

| ![New TributaryLink, step 3][figure-17] |
|:--:|
| ***Figure 17.** New TributaryLink, step 3* |

[figure-17]: images/figure-create-tributary-link-hop.png

The next step is choosing the endpoints. For this example, we’re going to end the SDH connection in a tributary port of a PDHBoard. It could, of course, end in any port of any board, however this is the most common scenario.

| ![Choosing the endpoints][figure-18] |
|:--:|
| ***Figure 18.** Choosing the endpoints* |

[figure-18]: images/figure-create-tributary-link-endpoints.png

Finally, as an option, you can associate the newly created `TributaryLink` to a service instance. Note that this list will be populated only with objects of subclasses of `GenericSDHService` previously created in the Service Manager, as seen in the [Figure 19][figure-19].

| ![Optionally, relating the circuit to a service][figure-19] |
|:--:|
| ***Figure 19.** Optionally, relating the circuit to a service* |

[figure-19]: images/figure-create-tributary-link-service.png

> **Important**
>
> As an exercise for the reader, create Container and TributaryLinks using the alternate STM4-based route.

## Module Actions

### Delete Transport Link { #delete-transport-link }

> Applies to object instances of `GenericSDHTransportLink` subclasses.

| ![Delete Transport Link][figure-20] |
|:--:|
| ***Figure 20.** Delete Transport Link* |

[figure-20]: images/figure-delete-transport-link.png

### Delete Container Link { #delete-container-link }

> Applies to object instances of `GenericSDHContainerLink` subclasses.

| ![Delete Container Link][figure-21] |
|:--:|
| ***Figure 21.** Delete Container Link* |

[figure-21]: images/figure-delete-container-link.png

### Delete Tributary Link { #delete-tributary-link }

> Applies to object instances of `GenericSDHTributaryLink` subclasses.

| ![Delete Tributary Link][figure-22] |
|:--:|
| ***Figure 22.** Delete Tributary Link* |

[figure-22]: images/figure-delete-tributary-link.png

[^1]: [Synchronous Digital Hierarchy (SDH) Graphical Overview](http://www.cisco.com/c/en/us/support/docs/optical/synchronous-digital-hierarchy-sdh/28327-sdh-28327.html)
