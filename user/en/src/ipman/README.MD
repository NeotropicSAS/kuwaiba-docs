# IP Address Manager

The *IP Address Manager* is a tool designed to manage IP addresses efficiently. It allows storing both individual IP addresses and entire sub-networks along with their associated IPs. Through this tool, users can easily view which IP addresses are busy and which are available on a given network. In summary, the IP address manager facilitates the organization and control of the assignment of IP addresses, contributing to more effective management of the network infrastructure.

To open the *IP Address Manager* module, select *Options -> IP Address Manager* from the options menu.
|![pool menu option](images/menu-option.png)|
|:--:|
| **Figure 1.** IP Address Manager module selection in the general menu |

Once the *IP Address Manager* module is opened you can distinguish:
|![explore ipv4](images/ipman-main.png)|
|:--:|
| **Figure 2.** Overview of the IP Address Manager |

* **Explore from IPv4 Root:** Explorer for IPv4 address management.

|![explore ipv4](images/explore-ipv4.png)|
|:--:|
| **Figure 3.** Explorer button for IPv4 address management |

* **Explore from IPv6 Root:** Explorer for IPv6 address management.

|![explore ipv5](images/explore-ipv5.png)|
|:--:|
| **Figure 4.** Explorer button for IPv6 address management |

* **Search bar:** In the central part of the screen there is a search bar that allows you to search for a specific IP address or folder within the IPv4 and IPv6 collections.

|![search bar](images/search-bar.png)|
|:--:|
| **Figure 5.** Search bar |

* **IP Management:** Allows you to create new sub-networks or collections of sub-networks.

|![ip management](images/ip-management.png)|
|:--:|
| **Figure 6.** IP Management |

* **IP Explorer:** Allows you to view the elements related to a collection of IP addresses, including subnets and other collections of subnets.

|![ipman explorer](images/ipman-explorer.png)|
|:--:|
| **Figure 7.** IP Explorer |

* **Properties of the selected element:** Allows you to view the properties or characteristics of the selected element. By default, the image below is displayed.

|![ipv4 properties](images/ipv4-properties.png)|
|:--:|
| **Figure 8.** Selected element properties |

## Create a new folder of subnets

In the IP Management section, select the button shown in the image below to add a new folder of subnets.

|![new folder](images/ipman-new-folder.png)|
|:--:|
| **Figure 9.** IP Management |

This action will open the dialog box shown below, where the name of the new folder (collection) and a description of it are requested. The new added item will appear in the *IP Explorer* section.

|![new folder dialog](images/ipman-new-folder-dialog.png)|
|:--:|
| **Figure 11.** Dialog for creating a new folder of subnets |

## Create a new subnet

In the IP Management section, select the button shown in the image below to add a new subnet.

|![new sub-net](images/ipman-new-subnet.png)|
|:--:|
| **Figure 12.** IP Management |

This action will open the dialog box shown below, where the subnet base address and subnet prefix in CIDR format will be requested, along with a brief description. The same dialog will provide a description of the items to be configured, including the broadcast address, network address, number of hosts, and subnet mask, as shown in the dialog below. The new added item will appear in the *IP Explorer* section.
|![new sub-net dialog](images/ipman-new-subnet-dialog.png)|
|:--:|
| **Figure 13.** Dialog for creating a new sub-network |

## IP Explorer

In this segment we can manipulate both the collections of sub-networks and the added sub-networks. The available options are described below:

* **Options for subnet folder** ![subnet options](images/menu-pool-subred.png):
  * **Add a new subnet folder** ![button add folder](images/add-folder-button.png): Creates a new subnet folder
  within the current folder.
  * **Remove subnet folder** ![button remove folder](images/remove-folder-button.png): Remove the folder.
  * **Add a new subnet folder** ![button add subnet](images/add-subnet-button.png): Creates a new subnet within the folder.
  * **Add a new IP** ![button add single ip](images/add-single-ip-button.png): Create an IP address within a sub-network. This will open a dialog like the one shown in the figure below, where the IP to enter and a description are requested.
    |![new single IP](images/new-single-ip-dialog.png)|
    |:--:|
    | **Figure 14.** New IP |
  * **Add to favorites** ![button add favorites](images/add-to-favorites.png):This functionality will be available in future versions.

* **Options for subnet** ![new pool dialog](images/menu-subred.png):
  * **Add a new subnet** ![button add folder](images/add-subnet-button.png): Create a new subnet within the current subnet, example shown in *Figure 13*.
  * **Delete subnet** ![button remove folder](images/del-subnet.png): Delete the subnet.
  * **Split a subnet** ![button add subnet](images/split-subnet.png): Split a subnet based on the network prefix as shown below.
    |![split subnet dialog](images/split-subnet-dialog.png)|
    |:--:|
    | **Figure 15.** Split a sub-network |
  * **Add a new IP** ![button add single ip](images/add-single-ip-button.png): Create an IP address within a sub-network. This will open a dialog like the one shown in *Figure 16*, where the IP to enter and a description are requested.
    |![new IP address dialog](images/add-ip-dialog.png)|
    |:--:|
    | **Figure 16.** Create non-reserved IP address |
  * **Create non-reserved IP**: As shown below, an IP is created and it will be *not reserved*. After running this command successfully, the **Divide a subnet** option will be disabled.
  * **Create all IP addresses**: As shown in *Figure 17* the possible IP addresses are created for the selected sub-network, all the IPs created will be *not reserved*.
    |![new all IP address dialog](images/add-ip-all-dialog.png)|
    |:--:|
    | **Figure 17.** Create all IPs |
  * **Create Reserved IP**: As shown below, an IP is created and it will be *reserved*. After executing this command successfully, the **Divide a sub-network** option will be disabled.
    |![new IP address reserved dialog](images/add-ip-reserved-dialog.png)|
    |:--:|
    | **Figure 18.** Create reserved IP address |
  * **Add to favorites** ![button add favorites](images/add-to-favorites.png): This functionality will be available in future versions.

## Properties of the selected element

The default image changes depending on the selected element, providing detailed information about it.

* **Selected subnet collection:** The figure below shows the subnets and IP addresses created in the collection. You can also see if these addresses are free, indicated with the icon ![ip free](images/free-IP.png), and the reserved ones with ![ip reserved](images/reserved-ip.png). Basic information such as name and description is presented.

  |![subnet properties](images/selected-subnet-collection.png)|
  |:--:|
  | **Figure 19.** Properties of a collection of subnets |

* **Selected sub-network:** The figure below shows the sub-network with the created IP addresses. You can also see if these addresses are linked to any network element, indicated with the ![ip relates](images/ip-related.png) icon. Free IPs are distinguished with the icon ![ip free](images/free-IP.png), and reserved ones with ![ip reserved](images/reserved-ip.png). Other icons correspond to the validator logic used for the module. In addition, basic information is presented such as the name, creation date and quantitative data, such as the percentage of occupancy of the sub-network.

  |![subnet properties](images/subnet-properties.png)|
  |:--:|
  | **Figure 20.** Properties of a sub-network |