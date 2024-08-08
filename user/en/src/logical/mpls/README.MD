# MPLS Networks

Create MPLS (Multiprotocol Label Switching) topologies and create virtual circuits between network interfaces.

| ![MPLS Module][figure-mpls-module] |
|:--:|
| ***Figure 1.** MPLS Module* |

[figure-mpls-module]: images/figure-mpls-module.png

[Figure 2][figure-2] shows an example MPLS view.

| ![Example MPLS View][figure-2] |
|:--:|
| ***Figure 2.** Example MPLS View* |

[figure-2]: images/figure-sample-mpls-view.png

1. [Tools][mpls-view-tools].
2. Canvas.
3. View Options Panel and [Object Options Panel][object-options-panel].

[mpls-view-tools]: #tools
[object-options-panel]: ../../navigation/navman/index.html#object-options-panel

## Tools

| ![Tools][figure-3] |
|:--:|
| ***Figure 3.** Tools* |

[figure-3]: images/figure-tools.png

[Figure 3][figure-3] shows the tools to manage the MPLS views.

| Tool | Description |
| -- | -- |
| ![tool-1][tool-1] | Open view |
| ![tool-2][tool-2] | New view |
| ![tool-3][tool-3] | Remove view |
| ![tool-4][tool-4] | Add existing devices and MPLS links to the view |
| ![tool-5][tool-5] | New MPLS link |
| ![tool-6][tool-6] | Detect MPLS link between nodes |
| ![tool-7][tool-7] | Remove from database and view |
| ![tool-8][tool-8] | Remove from view |
| ![tool-9][tool-9] | Export as image |

[tool-1]: ./images/tool-1.png
[tool-2]: ./images/tool-2.png
[tool-3]: ./images/tool-3.png
[tool-4]: ./images/tool-4.png
[tool-5]: ./images/tool-5.png
[tool-6]: ./images/tool-6.png
[tool-7]: ./images/tool-7.png
[tool-8]: ./images/tool-8.png
[tool-9]: ./images/tool-9.png

## Creating a View

To create a new view click on the `New MPLS view` tool [Figure 4][figure-4].

| ![New MPLS view window][figure-4] |
|:--:|
| ***Figure 4.** New MPLS view window* |

[figure-4]: images/figure-new-mpls-view-window.png

Once the view is created, two routers will be added [Figure 5][figure-5], these are the ones that were used in the [physical circuit][creating-a-physical-circuit] that was built in the connectivity manager chapter.

[creating-a-physical-circuit]: ../../physical/connectivityman/index.html#creating-a-physical-circuit

| ![Add existing devices][figure-5] |
|:--:|
| ***Figure 5.** Add existing devices* |

[figure-5]: images/figure-add-existing-devices-window.png

[Figure 6][figure-6] shows the view with the two MPLS routers.

| ![View with two nodes][figure-6] |
|:--:|
| ***Figure 6.** View with two MPLSRouters* |

[figure-6]: images/figure-new-mpls-view-with-nodes.png

In the chapter about [New Logical Circuit][new-logical-circuit], an MPLS Link [Figure 7][figure-7] was created that we will add to this view.

[new-logical-circuit]: ../../logical/new-logical-circuit/index.html

| ![Existing MPLS Link][figure-7] |
|:--:|
| ***Figure 7.** Existing MPLS Link* |

[figure-7]: images/figure-mpls-link-relationships.png

Using the MPLS link detection tool between nodes [Figure 8][figure-8].

| ![View with two connections][figure-8] |
|:--:|
| ***Figure 8.** View with MPLSLink* |

[figure-8]: images/figure-new-mpls-view-with-connections.png

## Module Actions

### Delete MPLS Link

> Applies to object instances of `MPLSLink` subclasses.

| ![Delete MPLS Link][figure-9] |
|:--:|
| ***Figure 9.** Delete MPLS Link* |

[figure-9]: images/figure-delete-mpls-link.png

### Relate to VLAN

> Applies to object instances of `GenericPort` subclasses.

| ![Relate to VLAN][figure-10] |
|:--:|
| ***Figure 10.** Relate to VLAN* |

[figure-10]: images/figure-relate-to-vlan.png
